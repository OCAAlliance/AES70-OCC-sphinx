.. _ocagroup:

1.2.22  OcaGroup
================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaGroup <ocagroup>`

.. cpp:class:: OcaGroup: OcaAgent

    Control aggregator. See **[AES70-1(Control Aggregation)]** for the normative
    specification of **OcaGroup** semantics.

    **Properties**:


    .. _ocagroup_aggregationrule:

    .. cpp:member:: OcaString AggregationRule

        Aggregation rule of group. Optional; null string if not used. Values are
        implementation-dependent.

        This property has id ``3.3``.

    .. _ocagroup_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.22"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocagroup_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 4

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocagroup_groupcontrollerono:

    .. cpp:member:: OcaONo GroupControllerONo

        Object number of group controller object. Zero value means group is peer
        to peer group in which a change to any member affects all members.

        This property has id ``3.2``.

    .. _ocagroup_members:

    .. cpp:member:: OcaList<OcaONo> Members

        Object numbers of group members

        This property has id ``3.1``.

    .. _ocagroup_saturationrule:

    .. cpp:member:: OcaString SaturationRule

        Saturation rule of group. Optional; null string if not used. Values are
        implementation-dependent.

        This property has id ``3.4``.

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


    .. _ocagroup_getmembers:

    .. cpp:function:: OcaStatus GetMembers(OcaList<OcaONo> &Members)

        Gets the list of Group members.

        This method has id ``3.1``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocagroup_setmembers:

    .. cpp:function:: OcaStatus SetMembers(OcaList<OcaONo> Members)

        Sets the list of Group members.

        This method has id ``3.2``.

        - :cpp:expr:`Members`: Input parameter.


    .. _ocagroup_addmember:

    .. cpp:function:: OcaStatus AddMember(OcaONo Member)

        Adds a Member to the Group.

        This method has id ``3.3``.

        - :cpp:expr:`Member`: Input parameter.


    .. _ocagroup_removemember:

    .. cpp:function:: OcaStatus RemoveMember(OcaONo Member)

        Removes a Member from the Group.

        This method has id ``3.4``.

        - :cpp:expr:`Member`: Input parameter.


    .. _ocagroup_getgroupcontrollerono:

    .. cpp:function:: OcaStatus GetGroupControllerONo(OcaONo &ONo)

        Gets the Group Controller object number.

        This method has id ``3.5``.

        - :cpp:expr:`ONo`: Output parameter.


    .. _ocagroup_setgroupcontrollerono:

    .. cpp:function:: OcaStatus SetGroupControllerONo(OcaONo ONo)

        Sets the Group Controller object number.

        This method has id ``3.6``.

        - :cpp:expr:`ONo`: Input parameter.


    .. _ocagroup_getaggregationrule:

    .. cpp:function:: OcaStatus GetAggregationRule(OcaString &Rule)

        Gets the value of the **AggregationRule** property.

        This method has id ``3.7``.

        - :cpp:expr:`Rule`: Output parameter.


    .. _ocagroup_setaggregationrule:

    .. cpp:function:: OcaStatus SetAggregationRule(OcaString Rule)

        Sets the value of the **AggregationRule** property.

        This method has id ``3.8``.

        - :cpp:expr:`Rule`: Input parameter.


    .. _ocagroup_getsaturationrule:

    .. cpp:function:: OcaStatus GetSaturationRule(OcaString &Rule)

        Gets the value of the **SaturationRule** property.

        This method has id ``3.9``.

        - :cpp:expr:`Rule`: Output parameter.


    .. _ocagroup_setsaturationrule:

    .. cpp:function:: OcaStatus SetSaturationRule(OcaString Rule)

        Sets the value of the **SaturationRule** property.

        This method has id ``3.10``.

        - :cpp:expr:`Rule`: Input parameter.


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


    .. _ocagroup_groupexception:

    .. cpp:function:: void GroupException(OcaGroupExceptionEventData eventData)

        Event that is emitted whenever a value-setting operation returns a
        status other than OK. NOTE. This is an ordinary event that causes a
        normal Notification message to be emitted. The OCP.1 protocol defines a
        special type of Notification PDU called **'Exception'**, but that PDU
        type is only used to signal cancellation of a subscription. This
        **GroupException** event uses the normal Notification PDU type, which is
        called **'Event'**.

        This event has id ``3.1``.
