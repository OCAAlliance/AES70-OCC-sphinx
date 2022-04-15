.. _ocatimesource:

1.2.16  OcaTimeSource
=====================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaTimeSource <ocatimesource>` 

.. cpp:class:: OcaTimeSource: OcaAgent

    A time source, internal or external. See RFC 7273 for a detailed discussion of time sources.

    **Properties**:

    .. _ocatimesource_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocatimesource_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

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

        Parameters (identifiers, modifiers, etc.) for this time source . Content is an SDP timestamp reference specification as defined in RFC7273, section 4.8.

        This property has id ``3.3``.

    .. _ocatimesource_referencetype:

    .. cpp:member:: OcaTimeReferenceType ReferenceType

        Type of time reference to which this time source is synced, if any.

        This property has id ``3.4``.

    .. _ocatimesource_referenceid:

    .. cpp:member:: OcaString ReferenceID

        Identifier of reference to which this time source is synced, if any. Not needed for all reference types.

        This property has id ``3.5``.

    .. _ocatimesource_syncstatus:

    .. cpp:member:: OcaTimeSourceSyncStatus SyncStatus

        Synchronization status of this time source.

        This property has id ``3.6``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocatimesource_getavailability:

    .. cpp:function:: OcaStatus GetAvailability(OcaTimeSourceAvailability &Availability)

        Gets the value of the  **Availability** property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.1``.

        :param OcaTimeSourceAvailability Availability: Output parameter.

    .. _ocatimesource_getprotocol:

    .. cpp:function:: OcaStatus GetProtocol(OcaTimeProtocol &Protocol)

        Gets the value of the  **Protocol** property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.2``.

        :param OcaTimeProtocol Protocol: Output parameter.

    .. _ocatimesource_setprotocol:

    .. cpp:function:: OcaStatus SetProtocol(OcaTimeProtocol Protocol)

        Sets the value of the  **Protocol** property. The return value indicates whether the value was successfully set.

        This method has id ``3.3``.

        :param OcaTimeProtocol Protocol: Input parameter.

    .. _ocatimesource_getparameters:

    .. cpp:function:: OcaStatus GetParameters(OcaSDPString &Parameters)

        Gets the value of the  **Parameters** property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.4``.

        :param OcaSDPString Parameters: Output parameter.

    .. _ocatimesource_setparameters:

    .. cpp:function:: OcaStatus SetParameters(OcaSDPString Parameters)

        Sets the value of the  **Parameters** property. The return value indicates whether the value was successfully set. Optional method, may not be supported in all implementations.

        This method has id ``3.5``.

        :param OcaSDPString Parameters: Input parameter.

    .. _ocatimesource_getreferencetype:

    .. cpp:function:: OcaStatus GetReferenceType(OcaTimeReferenceType &ReferenceType)

        Gets the time reference type. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.6``.

        :param OcaTimeReferenceType ReferenceType: Output parameter.

    .. _ocatimesource_setreferencetype:

    .. cpp:function:: OcaStatus SetReferenceType(OcaTimeReferenceType ReferenceType)

        Sets the time reference type. The return value indicates whether the value was successfully set. Optional method, may not be supported in all implementations.

        This method has id ``3.7``.

        :param OcaTimeReferenceType ReferenceType: Input parameter.

    .. _ocatimesource_getreferenceid:

    .. cpp:function:: OcaStatus GetReferenceID(OcaString &ID)

        Gets the timing source ID. The return value indicates whether the value was successfully retrieved. Optional method, not required for all time reference types.

        This method has id ``3.8``.

        :param OcaString ID: Output parameter.

    .. _ocatimesource_setreferenceid:

    .. cpp:function:: OcaStatus SetReferenceID(OcaString ID)

        Sets the time reference ID. The return value indicates whether the ID was successfully set. Optional method, not required for all time reference types.

        This method has id ``3.9``.

        :param OcaString ID: Input parameter.

    .. _ocatimesource_getsyncstatus:

    .. cpp:function:: OcaStatus GetSyncStatus(OcaTimeSourceSyncStatus &SyncStatus)

        Gets the synchronization status of this time source. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.10``.

        :param OcaTimeSourceSyncStatus SyncStatus: Output parameter.

    .. _ocatimesource_reset:

    .. cpp:function:: OcaStatus Reset()

        Resets this time source. Initiates a new synchronization sequence. The return value indicates whether the reset was successful.

        This method has id ``3.11``.



    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


