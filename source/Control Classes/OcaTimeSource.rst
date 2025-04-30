.. _ocatimesource:

1.2.16  OcaTimeSource
=====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaTimeSource <ocatimesource>`

.. cpp:class:: OcaTimeSource: OcaAgent

    A time source, internal or external, and the delivery method by which time
    values reach this device.

    **Properties**:


    .. _ocatimesource_availability:

    .. cpp:member:: OcaTimeSourceAvailability Availability

        Availability of this time source.

        This property has id ``3.1``.

    .. _ocatimesource_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.16"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocatimesource_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocatimesource_referencesdpdescription:

    .. cpp:member:: OcaSDPString ReferenceSDPDescription

        Parameters (identifiers, modifiers, etc.) for this time source . Content
        is an SDP time reference specification as defined in RFC7273, section
        4.8.

        This property has id ``3.3``.

    .. _ocatimesource_timedeliverymechanism:

    .. cpp:member:: OcaTimeDeliveryMechanism TimeDeliveryMechanism

        Time delivery mechanism used by this time source. Named **Protocol**
        prior to v3 of this class.

        This property has id ``3.2``.

    .. _ocatimesource_referenceid:

    .. cpp:member:: OcaString ReferenceID

        Identifier of reference to which this time source is synchronized, if
        any. Not needed for all time reference types. **This property is
        deprecated.**

        This property has id ``3.5``.

    .. _ocatimesource_referencetype:

    .. cpp:member:: OcaTimeReferenceType ReferenceType

        Type of time reference to which this time source is synchronized, if
        any. **This property is deprecated.**

        This property has id ``3.4``.

    .. _ocatimesource_syncstatus:

    .. cpp:member:: OcaTimeSourceSyncStatus SyncStatus

        Synchronization status of this time source.

        This property has id ``3.6``.

    .. _ocatimesource_timedeliveryparameters:

    .. cpp:member:: OcaParameterRecord TimeDeliveryParameters

        External parameter record for time delivery parameters. If
        **TimeDeliveryMechanism**=**StreamEndpoint**, then the schema of this
        parameter record shall be defined by the datatype
        **OcaTimeDeliveryParameters_StreamEndpoint**. Otherwise, the schema
        shall depend on the time delivery method chosen, and is out of scope of
        AES70-2.

        This property has id ``3.7``.

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


    .. _ocatimesource_getavailability:

    .. cpp:function:: OcaStatus GetAvailability(OcaTimeSourceAvailability &Availability)

        Gets the value of the **Availability** property.

        This method has id ``3.1``.

        - :cpp:expr:`Availability`: Output parameter.


    .. _ocatimesource_gettimedeliverymechanism:

    .. cpp:function:: OcaStatus GetTimeDeliveryMechanism(OcaTimeDeliveryMechanism &Mechanism)

        Gets the value of the **TimeDeliveryMechanism** property. Prior to v3 of
        this class, was named **GetProtocol.**

        This method has id ``3.2``.

        - :cpp:expr:`Mechanism`: Output parameter.


    .. _ocatimesource_settimedeliverymechanism:

    .. cpp:function:: OcaStatus SetTimeDeliveryMechanism(OcaTimeDeliveryMechanism Mechanism)

        Sets the value of the **TimeDeliveryMechanism** property. Prior to v3 of
        this class, was named **SetProtocol**.

        This method has id ``3.3``.

        - :cpp:expr:`Mechanism`: Input parameter.


    .. _ocatimesource_getreferencesdpdescription:

    .. cpp:function:: OcaStatus GetReferenceSDPDescription(OcaSDPString &Parameters)

        Gets the value of the **ReferenceSDPDescription** property.

        This method has id ``3.4``.

        - :cpp:expr:`Parameters`: Output parameter.


    .. _ocatimesource_setreferencesdpdescription:

    .. cpp:function:: OcaStatus SetReferenceSDPDescription(OcaSDPString Parameters)

        Sets the value of the **ReferenceSDPDescription** property. Optional
        method, may not be supported in all implementations.

        This method has id ``3.5``.

        - :cpp:expr:`Parameters`: Input parameter.


    .. _ocatimesource_getreferencetype:

    .. cpp:function:: OcaStatus GetReferenceType(OcaTimeReferenceType &ReferenceType)

        Gets the time reference type. **This method is deprecated.**

        This method has id ``3.6``.

        - :cpp:expr:`ReferenceType`: Output parameter.


    .. _ocatimesource_setreferencetype:

    .. cpp:function:: OcaStatus SetReferenceType(OcaTimeReferenceType ReferenceType)

        Sets the time reference type. Optional method, may not be supported in
        all implementations. **This method is deprecated.**

        This method has id ``3.7``.

        - :cpp:expr:`ReferenceType`: Input parameter.


    .. _ocatimesource_getreferenceid:

    .. cpp:function:: OcaStatus GetReferenceID(OcaString &ID)

        Gets the timing source ID. Optional method, not required for all time
        reference types.

        This method has id ``3.8``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocatimesource_setreferenceid:

    .. cpp:function:: OcaStatus SetReferenceID(OcaString ID)

        Sets the time reference ID. Optional method, not required for all time
        reference types.

        This method has id ``3.9``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocatimesource_getsyncstatus:

    .. cpp:function:: OcaStatus GetSyncStatus(OcaTimeSourceSyncStatus &SyncStatus)

        Gets the synchronization status of this time source.

        This method has id ``3.10``.

        - :cpp:expr:`SyncStatus`: Output parameter.


    .. _ocatimesource_reset:

    .. cpp:function:: OcaStatus Reset()

        Resets this time source. Initiates a new synchronization sequence.

        This method has id ``3.11``.

    .. _ocatimesource_gettimedeliveryparameters:

    .. cpp:function:: OcaStatus GetTimeDeliveryParameters(OcaParameterRecord &Record)

        Gets the value of the **TimeDeliveryParameters** property. Optional
        method.

        This method has id ``3.12``.

        - :cpp:expr:`Record`: Output parameter.


    .. _ocatimesource_settimedeliveryparameters:

    .. cpp:function:: OcaStatus SetTimeDeliveryParameters(OcaParameterRecord Record)

        Sets the value of the **TimeDeliveryParameters** property. Optional
        method.

        This method has id ``3.13``.

        - :cpp:expr:`Record`: Input parameter.


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

