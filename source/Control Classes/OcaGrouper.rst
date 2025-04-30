.. _ocagrouper:

1.2.2  OcaGrouper
=================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaGrouper <ocagrouper>`

.. cpp:class:: OcaGrouper: OcaAgent

    Control aggregator. See **[AES70-1(Control Aggregation)]** for the normative
    specification of **OcaGrouper** semantics. **Deprecated** in AES70-2024.

    **Properties**:


    .. _ocagrouper_actuatororsensor:

    .. cpp:member:: OcaBoolean ActuatorOrSensor

        True if Grouper is actuator grouper, false if sensor grouper.

        This property has id ``3.1``.

    .. _ocagrouper_citizens:

    .. cpp:member:: OcaList<OcaGrouperCitizen> Citizens

        List of citizens defined for this grouper.

        This property has id ``3.3``.

    .. _ocagrouper_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.2"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocagrouper_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocagrouper_enrollments:

    .. cpp:member:: OcaList<OcaGrouperEnrollment> Enrollments

        List of Grouper's enrollments, i.e. which Citizen(s) belong to which
        Group(s).

        This property has id ``3.4``.

    .. _ocagrouper_groups:

    .. cpp:member:: OcaList<OcaGrouperGroup> Groups

        List of groups in the grouper. Groups shall be added to and deleted from
        a grouper by the **OcaGrouper** methods **AddGroup(...)** and
        **DeleteGroup(...)**, respectively.

        This property has id ``3.2``.

    .. _ocagrouper_mode:

    .. cpp:member:: OcaGrouperMode Mode

        Switch that determines whether grouper is in hierarchical mode or
        peer-to-peer mode.

        This property has id ``3.5``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocagrouper_addgroup:

    .. cpp:function:: OcaStatus AddGroup(OcaString Name, OcaUint16 &Index, OcaONo &ProxyONo)

        Adds a group to the grouper and returns its object number. (The group's
        network address will be the same as the grouper's).

        This method has id ``3.1``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


        - :cpp:expr:`ProxyONo`: Output parameter.


    .. _ocagrouper_deletegroup:

    .. cpp:function:: OcaStatus DeleteGroup(OcaUint16 Index)

        Deletes a group from the grouper. Note: index values of deleted groups
        are not reused during the lifetime of the grouper instance.

        This method has id ``3.2``.

        - :cpp:expr:`Index`: Input parameter.


    .. _ocagrouper_getgroupcount:

    .. cpp:function:: OcaStatus GetGroupCount(OcaUint16 &Count)

        Gets the count of groups owned by this grouper.

        This method has id ``3.3``.

        - :cpp:expr:`Count`: Output parameter.


    .. _ocagrouper_getgrouplist:

    .. cpp:function:: OcaStatus GetGroupList(OcaList<OcaGrouperGroup> &GroupList)

        Gets the list of groups owned by this grouper.

        This method has id ``3.4``.

        - :cpp:expr:`GroupList`: Output parameter.


    .. _ocagrouper_addcitizen:

    .. cpp:function:: OcaStatus AddCitizen(OcaGrouperCitizen Citizen, OcaUint16 &CitizenIndex)

        Adds a citizen to the group. This method does not enroll the new citizen
        in any of the grouper's groups -- it merely makes the citizen available
        for enrollment. Group enrollment is controlled by the
        **SetEnrollment(...)** method, q.v.

        This method has id ``3.5``.

        - :cpp:expr:`Citizen`: Input parameter.


        - :cpp:expr:`CitizenIndex`: Output parameter.


    .. _ocagrouper_deletecitizen:

    .. cpp:function:: OcaStatus DeleteCitizen(OcaUint16 Index)

        Delete a citizen from the grouper (and therefore from all of its
        groups). Note: index values of deleted citizens are not reused during
        the lifetime of the grouper instance.

        This method has id ``3.6``.

        - :cpp:expr:`Index`: Input parameter.


    .. _ocagrouper_getcitizencount:

    .. cpp:function:: OcaStatus GetCitizenCount(OcaUint16 &Count)

        Gets the count of citizens registered in this grouper.

        This method has id ``3.7``.

        - :cpp:expr:`Count`: Output parameter.


    .. _ocagrouper_getcitizenlist:

    .. cpp:function:: OcaStatus GetCitizenList(OcaList<OcaGrouperCitizen> &List)

        Gets the list of citizens registered in this grouper.

        This method has id ``3.8``.

        - :cpp:expr:`List`: Output parameter.


    .. _ocagrouper_getenrollment:

    .. cpp:function:: OcaStatus GetEnrollment(OcaGrouperEnrollment Enrollment, OcaBoolean &IsMember)

        Gets membership status for given Citizen in given Group.

        This method has id ``3.9``.

        - :cpp:expr:`Enrollment`: Input parameter.


        - :cpp:expr:`IsMember`: Output parameter.


    .. _ocagrouper_setenrollment:

    .. cpp:function:: OcaStatus SetEnrollment(OcaGrouperEnrollment Enrollment, OcaBoolean IsMember)

        Sets membership status for given target in given group.

        This method has id ``3.10``.

        - :cpp:expr:`Enrollment`: Input parameter.


        - :cpp:expr:`IsMember`: Input parameter.


    .. _ocagrouper_getgroupmemberlist:

    .. cpp:function:: OcaStatus GetGroupMemberList(OcaUint16 Index, OcaList<OcaGrouperCitizen> &Members)

        Gets the list of members of the given group.

        This method has id ``3.11``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Members`: Output parameter.


    .. _ocagrouper_getactuatororsensor:

    .. cpp:function:: OcaStatus GetActuatorOrSensor(OcaBoolean &ActuatorOrSensor)

        Gets the value of the **ActuatorOrSensor** property.

        This method has id ``3.12``.

        - :cpp:expr:`ActuatorOrSensor`: Output parameter.


    .. _ocagrouper_setactuatororsensor:

    .. cpp:function:: OcaStatus SetActuatorOrSensor(OcaBoolean ActuatorOrSensor)

        Sets the value of the **ActuatorOrSensor** property. Note: only
        **Actuator** groups are supported in the current version of AES70.

        This method has id ``3.13``.

        - :cpp:expr:`ActuatorOrSensor`: Input parameter.


    .. _ocagrouper_getmode:

    .. cpp:function:: OcaStatus GetMode(OcaGrouperMode &Mode)

        Gets the value of the **Mode** property.

        This method has id ``3.14``.

        - :cpp:expr:`Mode`: Output parameter.


    .. _ocagrouper_setmode:

    .. cpp:function:: OcaStatus SetMode(OcaGrouperMode Mode)

        Sets the value of the **Mode** property.

        This method has id ``3.15``.

        - :cpp:expr:`Mode`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaAgent::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`


    **Events**:


    .. _ocagrouper_statuschange:

    .. cpp:function:: void StatusChange(OcaGrouperStatusChangeEventData eventData)

        Event that is emitted whenever key aspects of a group's status change.
        Status events include:

         - Citizen joins grouper

         - Citizen leaves grouper

         - Citizen fails to execute grouper value change request

         - Connection to online citizen is lost

         - Connection to offline citizen is reestablished

         - Citizen enrolls in group

         - Citizen de-enrolls from group



        This event has id ``3.1``.
