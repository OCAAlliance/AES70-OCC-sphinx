.. _ocanetwork:

1.2.1  OcaNetwork
=================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaNetwork <ocanetwork>` 

.. cpp:class:: OcaNetwork: OcaAgent

     **DEPRECATED CLASS**   *Replaced by class*  **OcaControlNetwork **  *in version 3 of Connection Management (CM3)*  Abstract base class for defining network classes to which this device belongs. This class is to be used for control and monitoring networks only. For media transport networks, and for networks that combine media transport and control, the  **OcaStreamNetwork**  class should be used instead.

    **Properties**:

    .. _ocanetwork_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocanetwork_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocanetwork_linktype:

    .. cpp:member:: OcaNetworkLinkType LinkType

        Network link type - e.g. wired Ethernet, USB, ... See the OcaNetworkType enum for details. This is a read-only property whose value is fixed to the class that is inherited from OcaNetwork to implement each specific type of network.

        This property has id ``3.1``.

    .. _ocanetwork_idadvertised:

    .. cpp:member:: OcaApplicationNetworkServiceID IDAdvertised

        ID by which this network object is known on the network, i.e. the name or GUID that this network object publishes in the network's directory/discovery system. As of OCA 1.4, this description has been clarified to indicate this property is the registered service name, which may or may not be the same as the device's host name, if any. For data network types that have host names (e.g. IP networks), the authoritative copy of the host name is in the system interface ID.

        This property has id ``3.2``.

    .. _ocanetwork_controlprotocol:

    .. cpp:member:: OcaNetworkControlProtocol ControlProtocol

        Type of control protocol used by the network (OCAnn) or NONE if this network is not used for control.

        This property has id ``3.3``.

    .. _ocanetwork_mediaprotocol:

    .. cpp:member:: OcaNetworkMediaProtocol MediaProtocol

        Deprecated property. Always has value NONE. Media transport is managed by the  **OcaStreamNetwork**  class.

        This property has id ``3.4``.

    .. _ocanetwork_status:

    .. cpp:member:: OcaNetworkStatus Status

        Operational status of the network.

        This property has id ``3.5``.

    .. _ocanetwork_systeminterfaces:

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceID> SystemInterfaces

        Collection of identifiers of system interface(s) used by the network. A "system interface" is the system service through which network traffic passes into and out of the device -- e.g. a socket. The identifier format is system and network dependent; for OCA purposes, it is maintained as a variable-length blob which the protocol does not inspect.

        This property has id ``3.6``.

    .. _ocanetwork_mediaports:

    .. cpp:member:: OcaList<OcaONo> MediaPorts

        Deprecated property. Always is empty. Media transport is now managed by the class  **OcaStreamNetwork.** 

        This property has id ``3.7``.

    .. _ocanetwork_statistics:

    .. cpp:member:: OcaNetworkStatistics Statistics

        Error statistics for this network

        This property has id ``3.8``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocanetwork_getlinktype:

    .. cpp:function:: OcaStatus GetLinkType(OcaNetworkLinkType &Type)

        Gets the network's link type (wired Ethernet, USB, etc.). Return status indicates whether the operation was successful.

        This method has id ``3.1``.

        :param OcaNetworkLinkType Type: Output parameter.

    .. _ocanetwork_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaApplicationNetworkServiceID &Name)

        Gets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``3.2``.

        :param OcaApplicationNetworkServiceID Name: Output parameter.

    .. _ocanetwork_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaApplicationNetworkServiceID Name)

        Sets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``3.3``.

        :param OcaApplicationNetworkServiceID Name: Input parameter.

    .. _ocanetwork_getcontrolprotocol:

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        Gets the network's ControlProtocol property. Return status indicates whether the operation was successful.

        This method has id ``3.4``.

        :param OcaNetworkControlProtocol Protocol: Output parameter.

    .. _ocanetwork_getmediaprotocol:

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        Gets the network's MediaProtocol property. This is a deprecated method that always returns the value NONE.

        This method has id ``3.5``.

        :param OcaNetworkMediaProtocol Protocol: Output parameter.

    .. _ocanetwork_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkStatus &Status)

        Retrieves the network's status. Return status indicates whether the status was successfully retrieved.

        This method has id ``3.6``.

        :param OcaNetworkStatus Status: Output parameter.

    .. _ocanetwork_getstatistics:

    .. cpp:function:: OcaStatus GetStatistics(OcaNetworkStatistics &Status)

        Retrieves network error statistics counter values. Return status indicates whether the values were successfully retrieved.

        This method has id ``3.7``.

        :param OcaNetworkStatistics Status: Output parameter.

    .. _ocanetwork_resetstatistics:

    .. cpp:function:: OcaStatus ResetStatistics()

        Resets network error statistics counters. Return status indicates whether the counters were successfully reset.

        This method has id ``3.8``.


    .. _ocanetwork_getsysteminterfaces:

    .. cpp:function:: OcaStatus GetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> &Interfaces)

        Gets the list of system interface IDs that this network is using. Return status indicates success of the operation.

        This method has id ``3.9``.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Output parameter.

    .. _ocanetwork_setsysteminterfaces:

    .. cpp:function:: OcaStatus SetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> Interfaces)

        Sets the list of system interface IDs that this network will use. Return status indicates success of the operation. This method is not implemented by all network implementations.

        This method has id ``3.10``.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Input parameter.

    .. _ocanetwork_getmediaports:

    .. cpp:function:: OcaStatus GetMediaPorts(OcaList<OcaONo> &Ports)

        Deprecated method. Always returns status INVALID_REQUEST. Media transport is now managed by the class  **OcaStreamNetwork.** 

        This method has id ``3.11``.

        :param OcaList<OcaONo> Ports: Output parameter.

    .. _ocanetwork_startup:

    .. cpp:function:: OcaStatus Startup()

        Start up this network.

        This method has id ``3.12``.


    .. _ocanetwork_shutdown:

    .. cpp:function:: OcaStatus Shutdown()

        Shut down this network.

        This method has id ``3.13``.



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
    
    


