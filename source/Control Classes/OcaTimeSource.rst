.. _ocatimesource:

1.2.16  OcaTimeSource
=====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaTimeSource <ocatimesource>`

.. cpp:class:: OcaTimeSource: OcaAgent

    A time source, internal or external. See RFC 7273 for a detailed discussion
    of time sources.

    **Properties**:


    .. _ocatimesource_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.16"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocatimesource_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1


        This property has id ``1.2``.

    .. _ocatimesource_availability:

    .. cpp:member:: OcaTimeSourceAvailability Availability

        Availability of this time source.

        This property has id ``3.1``.

    .. _ocatimesource_protocol:

    .. cpp:member:: OcaTimeProtocol Protocol

        Time transport protocol used by this time source

        This property has id ``3.2``.

    .. _ocatimesource_parameters:

    .. cpp:member:: OcaSDPString Parameters

        Parameters (identifiers, modifiers, etc.) for this time source . Content
        is an SDP timestamp reference specification as defined in RFC7273,
        section 4.8.

        This property has id ``3.3``.

    .. _ocatimesource_referencetype:

    .. cpp:member:: OcaTimeReferenceType ReferenceType

        Type of time reference to which this time source is synced, if any.

        This property has id ``3.4``.

    .. _ocatimesource_referenceid:

    .. cpp:member:: OcaString ReferenceID

        Identifier of reference to which this time source is synced, if any. Not
        needed for all reference types.

        This property has id ``3.5``.

    .. _ocatimesource_syncstatus:

    .. cpp:member:: OcaTimeSourceSyncStatus SyncStatus

        Synchronization status of this time source.

        This property has id ``3.6``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocatimesource_getavailability:

    .. cpp:function:: OcaStatus GetAvailability(OcaTimeSourceAvailability &Availability)

        Gets the value of the **Availability** property. The return value
        indicates whether the value was successfully retrieved.

        This method has id ``3.1``.

        - :cpp:expr:`Availability`: Output parameter.


    .. _ocatimesource_getprotocol:

    .. cpp:function:: OcaStatus GetProtocol(OcaTimeProtocol &Protocol)

        Gets the value of the **Protocol** property. The return value indicates
        whether the value was successfully retrieved.

        This method has id ``3.2``.

        - :cpp:expr:`Protocol`: Output parameter.


    .. _ocatimesource_setprotocol:

    .. cpp:function:: OcaStatus SetProtocol(OcaTimeProtocol Protocol)

        Sets the value of the **Protocol** property. The return value indicates
        whether the value was successfully set.

        This method has id ``3.3``.

        - :cpp:expr:`Protocol`: Input parameter.


    .. _ocatimesource_getparameters:

    .. cpp:function:: OcaStatus GetParameters(OcaSDPString &Parameters)

        Gets the value of the **Parameters** property. The return value
        indicates whether the value was successfully retrieved.

        This method has id ``3.4``.

        - :cpp:expr:`Parameters`: Output parameter.


    .. _ocatimesource_setparameters:

    .. cpp:function:: OcaStatus SetParameters(OcaSDPString Parameters)

        Sets the value of the **Parameters** property. The return value
        indicates whether the value was successfully set. Optional method, may
        not be supported in all implementations.

        This method has id ``3.5``.

        - :cpp:expr:`Parameters`: Input parameter.


    .. _ocatimesource_getreferencetype:

    .. cpp:function:: OcaStatus GetReferenceType(OcaTimeReferenceType &ReferenceType)

        Gets the time reference type. The return value indicates whether the
        value was successfully retrieved.

        This method has id ``3.6``.

        - :cpp:expr:`ReferenceType`: Output parameter.


    .. _ocatimesource_setreferencetype:

    .. cpp:function:: OcaStatus SetReferenceType(OcaTimeReferenceType ReferenceType)

        Sets the time reference type. The return value indicates whether the
        value was successfully set. Optional method, may not be supported in all
        implementations.

        This method has id ``3.7``.

        - :cpp:expr:`ReferenceType`: Input parameter.


    .. _ocatimesource_getreferenceid:

    .. cpp:function:: OcaStatus GetReferenceID(OcaString &ID)

        Gets the timing source ID. The return value indicates whether the value
        was successfully retrieved. Optional method, not required for all time
        reference types.

        This method has id ``3.8``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocatimesource_setreferenceid:

    .. cpp:function:: OcaStatus SetReferenceID(OcaString ID)

        Sets the time reference ID. The return value indicates whether the ID
        was successfully set. Optional method, not required for all time
        reference types.

        This method has id ``3.9``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocatimesource_getsyncstatus:

    .. cpp:function:: OcaStatus GetSyncStatus(OcaTimeSourceSyncStatus &SyncStatus)

        Gets the synchronization status of this time source. The return value
        indicates whether the value was successfully retrieved.

        This method has id ``3.10``.

        - :cpp:expr:`SyncStatus`: Output parameter.


    .. _ocatimesource_reset:

    .. cpp:function:: OcaStatus Reset()

        Resets this time source. Initiates a new synchronization sequence. The
        return value indicates whether the reset was successful.

        This method has id ``3.11``.

    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

