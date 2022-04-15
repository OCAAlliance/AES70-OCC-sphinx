.. _ocastreamnetwork:

1.2.10  OcaStreamNetwork
========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaStreamNetwork <ocastreamnetwork>` 

.. cpp:class:: OcaStreamNetwork: OcaAgent

     **DEPRECATED CLASS**   *Replaced by class*  **OcaMediaTransportNetwork **  *in version 3 of Connection Management (CM3)*  Abstract base class for defining network classes to which this device belongs. May be a media transport network, a control and monitoring network, or a network that does both. There shall be one OcaStreamNetwork instance for each network to which the device belongs. This class may be subclassed to support networks of various types.

    **Properties**:

    .. _ocastreamnetwork_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.10"

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocastreamnetwork_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocastreamnetwork_controlprotocol:

    .. cpp:member:: OcaNetworkControlProtocol ControlProtocol

        Type of control protocol used by the network (OCAnn) or NONE if this network is not used for control.

        This property has id ``3.3``.

    .. _ocastreamnetwork_idadvertised:

    .. cpp:member:: OcaNetworkNodeID IDAdvertised

        ID by which this device is known on the network, i.e. the host name or GUID that this device publishes in the network's directory/discovery system.

        This property has id ``3.2``.

    .. _ocastreamnetwork_linktype:

    .. cpp:member:: const OcaNetworkLinkType LinkType

        Network link type - e.g. wired Ethernet, USB, ... See the OcaNetworkType enum for details. This is a read-only property whose value is fixed to the class that is inherited from OcaNetwork to implement each specific type of network.

        This property has id ``3.1``.

    .. _ocastreamnetwork_mediaprotocol:

    .. cpp:member:: OcaNetworkMediaProtocol MediaProtocol

        Type of media transport protocol used by the network, or NONE if this network is not used for media transport.

        This property has id ``3.4``.

    .. _ocastreamnetwork_signalchannelssink:

    .. cpp:member:: OcaList<OcaONo> SignalChannelsSink

        List of object numbers of  _sink_  **OcaNetworkSignalChannel** objects collected by this network.

        This property has id ``3.10``.

    .. _ocastreamnetwork_signalchannelssource:

    .. cpp:member:: OcaList<OcaONo> SignalChannelsSource

        List of object numbers of  _source_  **OcaNetworkSignalChannel** objects collected by this network.

        This property has id ``3.9``.

    .. _ocastreamnetwork_statistics:

    .. cpp:member:: OcaNetworkStatistics Statistics

        Error statistics for this network

        This property has id ``3.11``.

    .. _ocastreamnetwork_status:

    .. cpp:member:: OcaNetworkStatus Status

        Operational status of the network.

        This property has id ``3.5``.

    .. _ocastreamnetwork_streamconnectorssink:

    .. cpp:member:: OcaList<OcaONo> StreamConnectorsSink

        List of object numbers of  _sink_  **OcaStreamConnector** objects collected by this network.

        This property has id ``3.8``.

    .. _ocastreamnetwork_streamconnectorssource:

    .. cpp:member:: OcaList<OcaONo> StreamConnectorsSource

        List of object numbers of  _source_  **OcaStreamConnector** objects collected by this network.

        This property has id ``3.7``.

    .. _ocastreamnetwork_systeminterfaces:

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceID> SystemInterfaces

        Collection of identifiers of system interface(s) used by the network. A "system interface" is the system service through which network traffic passes into and out of the device -- e.g. a socket. The identifier format is system and network dependent; for OCA purposes, it is maintained as a variable-length blob which the protocol does not inspect.

        This property has id ``3.6``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocastreamnetwork_getlinktype:

    .. cpp:function:: OcaStatus GetLinkType(OcaNetworkLinkType &Type)

        Gets the network's link type (wired Ethernet, USB, etc.). Return status indicates whether the operation was successful.

        This method has id ``3.1``.

        :param OcaNetworkLinkType Type: Output parameter.

    .. _ocastreamnetwork_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaNetworkNodeID &Name)

        Gets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``3.2``.

        :param OcaNetworkNodeID Name: Output parameter.

    .. _ocastreamnetwork_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaNetworkNodeID Name)

        Sets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``3.3``.

        :param OcaNetworkNodeID Name: Input parameter.

    .. _ocastreamnetwork_getcontrolprotocol:

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        Gets the network's ControlProtocol property. Return status indicates whether the operation was successful.

        This method has id ``3.4``.

        :param OcaNetworkControlProtocol Protocol: Output parameter.

    .. _ocastreamnetwork_getmediaprotocol:

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        Gets the network's MediaProtocol property. Return status indicates whether the operation was successful.

        This method has id ``3.5``.

        :param OcaNetworkMediaProtocol Protocol: Output parameter.

    .. _ocastreamnetwork_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkStatus &Status)

        Retrieves the network's status. Return status indicates whether the status was successfully retrieved.

        This method has id ``3.6``.

        :param OcaNetworkStatus Status: Output parameter.

    .. _ocastreamnetwork_getstatistics:

    .. cpp:function:: OcaStatus GetStatistics(OcaNetworkStatistics &Status)

        Retrieves network error statistics counter values. Return status indicates whether the values were successfully retrieved.

        This method has id ``3.7``.

        :param OcaNetworkStatistics Status: Output parameter.

    .. _ocastreamnetwork_resetstatistics:

    .. cpp:function:: OcaStatus ResetStatistics()

        Resets network error statistics counters. Return status indicates whether the counters were successfully reset.

        This method has id ``3.8``.


    .. _ocastreamnetwork_getsysteminterfaces:

    .. cpp:function:: OcaStatus GetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> &Interfaces)

        Gets the list of system interface IDs that this network is using. Return status indicates success of the operation.

        This method has id ``3.9``.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Output parameter.

    .. _ocastreamnetwork_setsysteminterfaces:

    .. cpp:function:: OcaStatus SetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> Interfaces)

        Sets the list of system interface IDs that this network will use. Return status indicates success of the operation. This method is not implemented by all network implementations.

        This method has id ``3.10``.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Input parameter.

    .. _ocastreamnetwork_getstreamconnectorssource:

    .. cpp:function:: OcaStatus GetStreamConnectorsSource(OcaList<OcaONo> &StreamConnectors)

        Gets the list of object numbers of Source  **OcaStreamConnector** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaStreamConnector** objects'  **Owner**  properties are updated, or when  **OcaStreamConnector**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.11``.

        :param OcaList<OcaONo> StreamConnectors: Output parameter.

    .. _ocastreamnetwork_setstreamconnectorssource:

    .. cpp:function:: OcaStatus SetStreamConnectorsSource(OcaList<OcaONo> StreamConnectors)

        Sets the list of object numbers of Source  **OcaStreamConnector** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaStreamConnector** objects'  **Owner**  properties are updated, or when  **OcaStreamConnector**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.12``.

        :param OcaList<OcaONo> StreamConnectors: Input parameter.

    .. _ocastreamnetwork_getstreamconnectorssink:

    .. cpp:function:: OcaStatus GetStreamConnectorsSink(OcaList<OcaONo> &StreamConnectors)

        Gets the list of object numbers of Sink  **OcaStreamConnector** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaStreamConnector**  objects'  **Owner**  properties are updated, or when  **OcaStreamConnector** objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.13``.

        :param OcaList<OcaONo> StreamConnectors: Output parameter.

    .. _ocastreamnetwork_setstreamconnectorssink:

    .. cpp:function:: OcaStatus SetStreamConnectorsSink(OcaList<OcaONo> StreamConnectors)

        Sets the list of object numbers of Sink  **OcaStreamConnector** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaStreamConnector**  objects'  **Owner**  properties are updated, or when  **OcaStreamConnector**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.14``.

        :param OcaList<OcaONo> StreamConnectors: Input parameter.

    .. _ocastreamnetwork_getsignalchannelssource:

    .. cpp:function:: OcaStatus GetSignalChannelsSource(OcaList<OcaONo> &SignalChannels)

        Gets the list of object numbers of Source  **OcaNetworkSignalChannel** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaNetworkSignalChannel**  objects'  **Owner**  properties are updated, or when  **OcaNetworkSignalChannel**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.15``.

        :param OcaList<OcaONo> SignalChannels: Output parameter.

    .. _ocastreamnetwork_setsignalchannelssource:

    .. cpp:function:: OcaStatus SetSignalChannelsSource(OcaList<OcaONo> SignalChannels)

        Sets the list of object numbers of Source  **OcaNetworkSignalChannel** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaNetworkSignalChannel**  objects'  **Owner**  properties are updated, or when  **OcaNetworkSignalChannel**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.16``.

        :param OcaList<OcaONo> SignalChannels: Input parameter.

    .. _ocastreamnetwork_getsignalchannelssink:

    .. cpp:function:: OcaStatus GetSignalChannelsSink(OcaList<OcaONo> &SignalChannels)

        Gets the list of object numbers of Sink  **OcaNetworkSignalChannel** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaNetworkSignalChannel**  objects'  **Owner**  properties are updated, or when  **OcaNetworkSignalChannel**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.17``.

        :param OcaList<OcaONo> SignalChannels: Output parameter.

    .. _ocastreamnetwork_setsignalchannelssink:

    .. cpp:function:: OcaStatus SetSignalChannelsSink(OcaList<OcaONo> SignalChannels)

        Sets the list of object numbers of Sink  **OcaNetworkSignalChannel** objects owned by this network. Return status indicates success of the operation. If the value of the network's MediaProtocol property is NONE, this method will return the status value InvalidRequest. Members are added to and deleted from this list when  **OcaNetworkSignalChannel**  objects'  **Owner**  properties are updated, or when  **OcaNetworkSignalChannel**  objects are deleted. For reconfigurable devices, such changes may be initiated by controllers during device operation.

        This method has id ``3.18``.

        :param OcaList<OcaONo> SignalChannels: Input parameter.

    .. _ocastreamnetwork_startup:

    .. cpp:function:: OcaStatus Startup()

        Start up this network.

        This method has id ``3.19``.


    .. _ocastreamnetwork_shutdown:

    .. cpp:function:: OcaStatus Shutdown()

        Shut down this network.

        This method has id ``3.20``.



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
    
    


