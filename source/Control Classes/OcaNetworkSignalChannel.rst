.. _ocanetworksignalchannel:

1.1.6  OcaNetworkSignalChannel
==============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaNetworkSignalChannel <ocanetworksignalchannel>` 

.. cpp:class:: OcaNetworkSignalChannel: OcaWorker

     **DEPRECATED CLASS**   *Replaced by features of the*  **OcaMediaSinkConnector **  *and*  **OcaMediaSourceConnector **  *datatypes in version 3 of Connection Management (CM3)*  Worker that allows connection of one or more internal signal paths to a network signal channel.  
    
     - For stream-oriented media connection management such as used by AVB, this worker will be linked to an  **OcaStreamConnector**  object and to the appropriate  **OcaStreamNetwork** object.
     
    
     - For channel-oriented media connection management, such as the Dante name-based routing mechanism, this worker will be linked only to the  **OcaStreamNetwork** object.
     

    **Properties**:

    .. _ocanetworksignalchannel_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.6"

        ID of this class

        This property has id ``3.1``.

    .. _ocanetworksignalchannel_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Version number of this class

        This property has id ``3.2``.

    .. _ocanetworksignalchannel_connectorpins:

    .. cpp:member:: OcaMap<OcaONo, OcaStreamConnectorPinIndex> ConnectorPins

        Map of object numbers of  **OcaStreamConnector**  objects to  **OcaStreamConnectorPinIndex** of these connectors. This map identifies which  **OcaStreamConnector**  objects contain this network signal channel, and indicates at what pin of the connector this channel is found. If the  **OcaNetworkSignalChannel**  object is not part of any  **OcaStreamConnector** this map is empty. Note that  **OcaNetworkSignalChannel**  objects of type  **Sink**  cannot have more than one entry in the map, else it would implicitly perform mixing.  **OcaNetworkSignalChannel** objects of type  **Source**  can have multiple entries in the map.

        This property has id ``3.3``.

    .. _ocanetworksignalchannel_idadvertised:

    .. cpp:member:: OcaNetworkSignalChannelID IDAdvertised

        Character name or binary identifier of the port that is advertised on the network to be found by other devices' discovery processes. Depending on the media transport architecture being used, this ID may be globally unique throughout the network, or only unique within the scope of the specific Network instance to which the port is attached.

        This property has id ``3.1``.

    .. _ocanetworksignalchannel_network:

    .. cpp:member:: OcaONo Network

        Object number of stream network object ( **OcaStreamNetwork**  or one of its subclasses) to which this signal channel belongs.

        This property has id ``3.2``.

    .. _ocanetworksignalchannel_remotechannelid:

    .. cpp:member:: OcaNetworkSignalChannelID RemoteChannelID

        External ID of ultimate source or destination of signal.

        This property has id ``3.4``.

    .. _ocanetworksignalchannel_sourceorsink:

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        Describes whether this signal channel is source (emits signals into the network) or sink (receives signals from the network). Sources are sometimes called "talkers", and sinks are sometimes called "listeners".

        This property has id ``3.5``.

    .. _ocanetworksignalchannel_status:

    .. cpp:member:: OcaNetworkSignalChannelStatus Status

        Status of the port

        This property has id ``3.6``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocanetworksignalchannel_addtoconnector:

    .. cpp:function:: OcaStatus AddToConnector(OcaONo Connector, OcaStreamConnectorPinIndex Index)

        Adds the object number of the stream connector object to which this media port belongs, and specifies on what index of the stream connector this channel can be found. Return status indicates success of operation.

        This method has id ``3.6``.

        :param OcaONo Connector: Input parameter.
        :param OcaStreamConnectorPinIndex Index: Input parameter.

    .. _ocanetworksignalchannel_getconnectorpins:

    .. cpp:function:: OcaStatus GetConnectorPins(OcaMap<OcaONo, OcaStreamConnectorPinIndex> &ConnectorPins)

        Gets the object number of the stream connector object to which this media port belongs, if any. If port does not belong to a stream connector, returns zero. Return status indicates success of operation.

        This method has id ``3.5``.

        :param OcaMap<OcaONo, OcaStreamConnectorPinIndex> ConnectorPins: Output parameter.

    .. _ocanetworksignalchannel_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaNetworkSignalChannelID &IDAdvertised)

        Gets the value of the IDAdvertised property. Return status indicates success of operation.

        This method has id ``3.1``.

        :param OcaNetworkSignalChannelID IDAdvertised: Output parameter.

    .. _ocanetworksignalchannel_getnetwork:

    .. cpp:function:: OcaStatus GetNetwork(OcaONo &Network)

        Gets the object number of the stream network object to which this media port belongs. Return status indicates success of operation.

        This method has id ``3.3``.

        :param OcaONo Network: Output parameter.

    .. _ocanetworksignalchannel_getremotechannelid:

    .. cpp:function:: OcaStatus GetRemoteChannelID(OcaNetworkSignalChannelID &RemoteChannelID)

        Gets the remote channel ID to which this channel is connected. Empty if the channel is not connected (at least not directly to another channel). For stream-oriented connection management this functionality is not used (i.e. the remote channel ID will always be empty).

        This method has id ``3.8``.

        :param OcaNetworkSignalChannelID RemoteChannelID: Output parameter.

    .. _ocanetworksignalchannel_getsourceorsink:

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        Gets the value of the SourceOrSink property. Return status indicates success of operation.

        This method has id ``3.10``.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Output parameter.

    .. _ocanetworksignalchannel_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkSignalChannelStatus &Status)

        Gets the value of the Status property. Return status indicates success of operation.

        This method has id ``3.11``.

        :param OcaNetworkSignalChannelStatus Status: Output parameter.

    .. _ocanetworksignalchannel_removefromconnector:

    .. cpp:function:: OcaStatus RemoveFromConnector(OcaONo Connector)

        Removes this channel from the passed stream connector. Return status indicates success of operation.

        This method has id ``3.7``.

        :param OcaONo Connector: Input parameter.

    .. _ocanetworksignalchannel_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaNetworkSignalChannelID IDAdvertised)

        Sets the value of the IDAdvertised property. Return status indicates success of operation.

        This method has id ``3.2``.

        :param OcaNetworkSignalChannelID IDAdvertised: Input parameter.

    .. _ocanetworksignalchannel_setnetwork:

    .. cpp:function:: OcaStatus SetNetwork(OcaONo Network)

        Sets the object number of the stream network object to which this media port belongs. Return status indicates success of operation. Only implemented for reconfigurable devices.

        This method has id ``3.4``.

        :param OcaONo Network: Input parameter.

    .. _ocanetworksignalchannel_setremotechannelid:

    .. cpp:function:: OcaStatus SetRemoteChannelID(OcaNetworkSignalChannelID RemoteChannelID)

        Sets the remote channel ID to which this channel must be connected. Only used for channel-oriented connection management. For stream-oriented connection management this method is not used. Clearing the remote channel ID (i.e. tearing down the connection) can be done by passing an empty remote channel ID as parameter.

        This method has id ``3.9``.

        :param OcaNetworkSignalChannelID RemoteChannelID: Input parameter.


    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


