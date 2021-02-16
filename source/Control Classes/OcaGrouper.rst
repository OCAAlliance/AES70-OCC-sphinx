.. _ocagrouper:

1.2.2  OcaGrouper
=================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaGrouper: OcaAgent

    **Concept** ** ** A **grouper** is an object responsible for
    aggregating property values. An **actuator grouper** allows control of
    many actuator objects from a single input value; a **sensor grouper**
    allows observing many sensor objects via a single output value.
    Actuator groupers are described below; sensor groupers are TBD. In a
    working media system, many actuator objects (we will call them
    **citizens** ) will be members of multiple groups. For example, in a
    multiway stereo sound reinforcement system, the left woofer power
    amplifier might be controlled by a master gain group, a left-side gain
    group, and a woofer gain group. To manage the interactions of these
    multiple memberships, we need a single entity that manages all three
    of these groups, anticipating the interactions and taking appropriate
    action. An actuator grouper is such an entity. The grouper:
    
    - Registers all the groups and all the citizens.
    
    
    - Remembers which citizens belong to which groups.
    
    
    - Computes new property values when group settings change.
    
    
    - Manages overrange and underrange conditions proactively, so that
    citizens are never asked to assume out of range values.
    For any given grouper instance, all of its citizens will all be of the
    same class. Applications may have a number of grouper instances, one
    for each citizen class -- an OcaGain grouper, an OcaFrequency grouper,
    etc. For controlling each group, the grouper creates a proxy object of
    the same class as its citizens, so that the same controller logic can
    be used for either a group or an individual worker. It may be helpful
    to visualize a grouper as a matrix whose rows are groups, columns are
    citizens, and each cell contains information relating to the
    membership of the citizen in the group. This information is called the
    citizen's **enrollment** in the group. **Mechanism** Each Grouper is
    an instance of this class ( **OcaGrouper** ). A **group** is a
    collection of citizens. A citizen that belongs to a group is called a
    **member** of that group. There is a many-to-many relationship between
    groups and citizens -- any citizen can be a member of any number of
    groups. The purpose of the Grouper is to contain the set of groups and
    the set of citizens, to remember which citizens belong to which
    groups, and to compute new aggregate values when settings or readings
    change. The Grouper itself does not provide direct access to parameter
    data values. That access is provided by **group proxies** or by **peer
    to peer** mastering -- see below. It is useful to think of a Grouper
    as a matrix in which groups are rows and citizens are columns. A cell
    of the matrix is nonempty whenever its column (=citizen) belongs to
    its row (=group). Such a cell is called an **enrollment.** **Classes
    of Grouped Objects** Group members can be actuator or sensor objects.
    A group whose members are actuators is called an **actuator group** .
    A group whose members are sensors is called a **sensor group** . All
    the citizens of a given Grouper must be of the same worker class
    (sounds communistic, doesn't it :) called the **citizen class** .
    Typically an application will have multiple Groupers, each one
    supporting a different citizen class. **Adding Groups** New groups can
    be added to the Grouper at any time, using OcaGrouper's **AddGroup**
    method. **Group Proxies; Peer to Peer Mastering** Depending on the
    setting of its **mode** property, a grouper may be in **master-slave
    mode** or **peer to peer mode.** _In master-slave mode_ , each time a
    caller adds a group to a Grouper instance, the Grouper instance
    creates an object known as a **group proxy.** Thus, there is one group
    proxy instance per group.The class of the group proxy is the same as
    the Grouper's citizen class. For example, for a group of OcaGain
    actuators, the group proxy is an OcaGain object. The purpose of the
    group proxy is to allow controllers to access the group's setpoint
    (for actuator groups) or reading (for sensor groups) in the same way
    as they would access individual workers of the citizen class. _In
    peer-to-peer mode_ , no group proxy is created. Instead, the group
    setpoint is changed whenever *any* member's setpoint is changed. In
    effect, all the group's members behave as though they were group
    proxies. **Adding Citizens** New citizens may be added to a Grouper
    instance at any time, using OcaGrouper's **AddCitizen** method.
    Newly-added citizens are by default not members of any group. Citizens
    may be enrolled in groups at any time using OcaGrouper's
    **SetEnrollment** method. **Deleting** The Grouper allows deletion of
    groups and citizens at any time, although excessive deletion may lead
    to sparse memory use, depending on Grouper implementation.
    **Setpoints, Readings, and Aggregation** **Setpoints and Rules** Each
    group has a **setpoint** (for actuator groups) or **reading** (for
    sensor groups) whose value is related to its members' setpoints or
    readings by the combination of two rules:
    
    - The group's **saturation rules** , which control handling of
    overrange conditions; and
    
    
    - Each member's **aggregation rules** , which determine the algorithms
    by which aggregate values are computed.
    ** ** **Scope of the OcaGrouper Class** Many aspects of groupers will
    vary from product to product. **OcaGrouper** is an abstract class that
    defines common concepts and terms for groupers, a canonical control
    interface, and most aspects of membership management . However it but
    stops short of specifying actual semantics. Implementations will need
    to define (at least):
    
    - Saturation rules
    
    
    - Aggregation rules
    
    
    - Error-handling mechanisms (e.g. what happens when a grouper loses
    its connection to a citizen, and what happens when it later
    re-attaches)
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaBoolean ActuatorOrSensor

        This property has id ``3.0``.

        True if Grouper is actuator grouper, false if sensor grouper.

    .. cpp:member:: OcaList<OcaGrouperGroup> Groups

        This property has id ``3.0``.

        List of groups in the grouper. Groups are added to and deleted from a
        grouper by the AdGroup and DeleteGroup methods of OcaGrouper.

    .. cpp:member:: OcaList<OcaGrouperCitizen> Citizens

        This property has id ``3.0``.

        List of citizens defined for this grouper.

    .. cpp:member:: OcaList<OcaGrouperEnrollment> Enrollments

        This property has id ``3.0``.

        List of grouper's enrollments, i.e. which citizen(s) belong to which
        group(s).

    .. cpp:member:: OcaGrouperMode Mode

        This property has id ``3.0``.

        Switch that determines whether grouper is in master-slave mode or
        peer-to-peer mode.

    .. cpp:function:: OcaStatus AddGroup(OcaString Name, OcaUint16 &Index, OcaONo &ProxyONo)

        This method has id ``3.1``.

        Adds a group to the grouper and returns its object number. (The
        group's network address will be the same as the grouper's). The return
        value indicates whether the group was successfully added.

        :param OcaString Name: Input parameter.
        :param OcaUint16 Index: Output parameter.
        :param OcaONo ProxyONo: Output parameter.

    .. cpp:function:: OcaStatus DeleteGroup(OcaUint16 Index)

        This method has id ``3.2``.

        Deletes a group from the grouper. The return value indicates whether
        the group was successfully deleted. Note: index values of deleted
        groups are not reused during the lifetime of the grouper instance.

        :param OcaUint16 Index: Input parameter.

    .. cpp:function:: OcaStatus GetGroupCount(OcaUint16 &Count)

        This method has id ``3.3``.

        Gets the count of groups owned by this grouper. The return value
        indicates whether the count was successfully retrieved.

        :param OcaUint16 Count: Output parameter.

    .. cpp:function:: OcaStatus GetGroupList(OcaList<OcaGrouperGroup> &GroupList)

        This method has id ``3.4``.

        Gets the list of groups owned by this grouper. The return value
        indicates whether the list was successfully retrieved.

        :param OcaList<OcaGrouperGroup> GroupList: Output parameter.

    .. cpp:function:: OcaStatus AddCitizen(OcaGrouperCitizen Citizen, OcaUint16 &CitizenIndex)

        This method has id ``3.5``.

        Adds a target to the group. The return value indicates whether the
        target was successfully added. This method does not enroll the new
        target in any of the grouper's groups -- it merely makes the target
        available for enrollment. Group membership is controlled by the
        SetEnrollment method, q.v.

        :param OcaGrouperCitizen Citizen: Input parameter.
        :param OcaUint16 CitizenIndex: Output parameter.

    .. cpp:function:: OcaStatus DeleteCitizen(OcaUint16 Index)

        This method has id ``3.6``.

        Delete a citizen from the grouper (and therefore from all of its
        groups). The return value indicates whether the citizen was
        successfully deleted. Note: index values of deleted citizens are not
        reused during the lifetime of the grouper instance.

        :param OcaUint16 Index: Input parameter.

    .. cpp:function:: OcaStatus GetCitizenCount(OcaUint16 &Count)

        This method has id ``3.7``.

        Gets the count of citizens registered in this grouper. The return
        value indicates whether the count was successfully retrieved.

        :param OcaUint16 Count: Output parameter.

    .. cpp:function:: OcaStatus GetCitizenList(OcaList<OcaGrouperCitizen> &List)

        This method has id ``3.8``.

        Gets the list of citizens registered in this grouper. The return value
        indicates whether the list was successfully retrieved.

        :param OcaList<OcaGrouperCitizen> List: Output parameter.

    .. cpp:function:: OcaStatus GetEnrollment(OcaGrouperEnrollment Enrollment, OcaBoolean &IsMember)

        This method has id ``3.9``.

        Gets membership status for given target in given group. The return
        value indicates whether the status was successfully retrieved.

        :param OcaGrouperEnrollment Enrollment: Input parameter.
        :param OcaBoolean IsMember: Output parameter.

    .. cpp:function:: OcaStatus SetEnrollment(OcaGrouperEnrollment Enrollment, OcaBoolean IsMember)

        This method has id ``3.10``.

        Sets membership status for given target in given group. The return
        value indicates whether the status was successfully set.

        :param OcaGrouperEnrollment Enrollment: Input parameter.
        :param OcaBoolean IsMember: Input parameter.

    .. cpp:function:: OcaStatus GetGroupMemberList(OcaUint16 Index, OcaList<OcaGrouperCitizen> &Members)

        This method has id ``3.11``.

        Gets the list of members of the given group. The return value
        indicates whether the list was successfully retrieved.

        :param OcaUint16 Index: Input parameter.
        :param OcaList<OcaGrouperCitizen> Members: Output parameter.

    .. cpp:function:: OcaStatus GetActuatorOrSensor(OcaBoolean &ActuatorOrSensor)

        This method has id ``3.12``.

        Gets the value of the ActuatorOrSensor property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaBoolean ActuatorOrSensor: Output parameter.

    .. cpp:function:: OcaStatus SetActuatorOrSensor(OcaBoolean ActuatorOrSensor)

        This method has id ``3.13``.

        Sets the value of the ActuatorOrSensor property. The return value
        indicates whether the value was successfully set.

        :param OcaBoolean ActuatorOrSensor: Input parameter.

    .. cpp:function:: OcaStatus GetMode(OcaGrouperMode &Mode)

        This method has id ``3.14``.

        Gets the value of the Mode property. The return value indicates
        whether the value was successfully retrieved.

        :param OcaGrouperMode Mode: Output parameter.

    .. cpp:function:: OcaStatus SetMode(OcaGrouperMode Mode)

        This method has id ``3.15``.

        Sets the value of the Mode property. The return value indicates
        whether the value was successfully set.

        :param OcaGrouperMode Mode: Input parameter.

