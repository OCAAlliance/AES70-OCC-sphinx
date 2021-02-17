.. _ocacontrolnetwork:

1.4.1  OcaControlNetwork
========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaApplicationNetwork <ocaapplicationnetwork>` :raw:html:`&rarr;` :ref:`OcaControlNetwork <ocacontrolnetwork>` 

.. cpp:class:: OcaControlNetwork: OcaApplicationNetwork


    **Properties**:

    .. _ocacontrolnetwork_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocacontrolnetwork_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property is an override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocacontrolnetwork_protocol:

    .. cpp:member:: OcaNetworkControlProtocol Protocol

        Type of control protocol used by the network (OCAnn). Read-only
        property.

        This property has id ``3.1``.

    Properties inherited from :ref:`OcaApplicationNetwork <OcaApplicationNetwork>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaApplicationNetwork::Label <OcaApplicationNetwork_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaApplicationNetwork::Owner <OcaApplicationNetwork_Owner>`
    
    - :cpp:texpr:`OcaApplicationNetworkServiceID` :ref:`OcaApplicationNetwork::ServiceID <OcaApplicationNetwork_ServiceID>`
    
    - :cpp:texpr:`OcaList<OcaNetworkSystemInterfaceDescriptor>` :ref:`OcaApplicationNetwork::SystemInterfaces <OcaApplicationNetwork_SystemInterfaces>`
    
    - :cpp:texpr:`OcaApplicationNetworkState` :ref:`OcaApplicationNetwork::State <OcaApplicationNetwork_State>`
    
    - :cpp:texpr:`OcaUint16` :ref:`OcaApplicationNetwork::ErrorCode <OcaApplicationNetwork_ErrorCode>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocacontrolnetwork_getcontrolprotocol:

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        Gets the network's Protocol property. Return status indicates whether
        the operation was successful.

        This method has id ``3.1``.

        :param OcaNetworkControlProtocol Protocol: Output parameter.


    Methods inherited from :ref:`OcaApplicationNetwork <OcaApplicationNetwork>`:
    
    - :ref:`OcaApplicationNetwork::GetLabel(Label) <OcaApplicationNetwork_GetLabel>`
    
    - :ref:`OcaApplicationNetwork::SetLabel(Label) <OcaApplicationNetwork_SetLabel>`
    
    - :ref:`OcaApplicationNetwork::GetOwner(Owner) <OcaApplicationNetwork_GetOwner>`
    
    - :ref:`OcaApplicationNetwork::GetServiceID(Name) <OcaApplicationNetwork_GetServiceID>`
    
    - :ref:`OcaApplicationNetwork::SetServiceID(Name) <OcaApplicationNetwork_SetServiceID>`
    
    - :ref:`OcaApplicationNetwork::GetSystemInterfaces(SystemInterfaces) <OcaApplicationNetwork_GetSystemInterfaces>`
    
    - :ref:`OcaApplicationNetwork::SetSystemInterfaces(Descriptors) <OcaApplicationNetwork_SetSystemInterfaces>`
    
    - :ref:`OcaApplicationNetwork::GetState(State) <OcaApplicationNetwork_GetState>`
    
    - :ref:`OcaApplicationNetwork::GetErrorCode(ErrorCode) <OcaApplicationNetwork_GetErrorCode>`
    
    - :ref:`OcaApplicationNetwork::Control(Command) <OcaApplicationNetwork_Control>`
    
    - :ref:`OcaApplicationNetwork::GetPath(NamePath, ONoPath) <OcaApplicationNetwork_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


