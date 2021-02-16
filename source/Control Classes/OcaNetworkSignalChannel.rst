.. _ocanetworksignalchannel:

1.1.6  OcaNetworkSignalChannel
==============================

Extends :ref:`OcaWorker <ocaworker>`.

.. cpp:class:: OcaNetworkSignalChannel: OcaWorker

    **DEPRECATED CLASS** *Replaced by features of the*
    **OcaMediaSinkConnector ** *and* **OcaMediaSourceConnector **
    *datatypes in version 3 of Connection Management (CM3)* Worker that
    allows connection of one or more internal signal paths to a network
    signal channel.
    
    - For stream-oriented media connection management such as used by AVB,
    this worker will be linked to an **OcaStreamConnector** object and to
    the appropriate **OcaStreamNetwork** object.
    
    
    - For channel-oriented media connection management, such as the Dante
    name-based routing mechanism, this worker will be linked only to the
    **OcaStreamNetwork** object.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        ID of this class

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Version number of this class

    .. cpp:member:: OcaMap<OcaONo, OcaStreamConnectorPinIndex> ConnectorPins

        This property has id ``3.3``.

        Map of object numbers of **OcaStreamConnector** objects to
        **OcaStreamConnectorPinIndex** of these connectors. This map
        identifies which **OcaStreamConnector** objects contain this network
        signal channel, and indicates at what pin of the connector this
        channel is found. If the **OcaNetworkSignalChannel** object is not
        part of any **OcaStreamConnector** this map is empty. Note that
        **OcaNetworkSignalChannel** objects of type **Sink** cannot have more
        than one entry in the map, else it would implicitly perform mixing.
        **OcaNetworkSignalChannel** objects of type **Source** can have
        multiple entries in the map.

    .. cpp:member:: OcaNetworkSignalChannelID IDAdvertised

        This property has id ``3.1``.

        Character name or binary identifier of the port that is advertised on
        the network to be found by other devices' discovery processes.
        Depending on the media transport architecture being used, this ID may
        be globally unique throughout the network, or only unique within the
        scope of the specific Network instance to which the port is attached.

    .. cpp:member:: OcaONo Network

        This property has id ``3.2``.

        Object number of stream network object ( **OcaStreamNetwork** or one
        of its subclasses) to which this signal channel belongs.

    .. cpp:member:: OcaNetworkSignalChannelID RemoteChannelID

        This property has id ``3.4``.

        External ID of ultimate source or destination of signal.

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        This property has id ``3.5``.

        Describes whether this signal channel is source (emits signals into
        the network) or sink (receives signals from the network). Sources are
        sometimes called "talkers", and sinks are sometimes called
        "listeners".

    .. cpp:member:: OcaNetworkSignalChannelStatus Status

        This property has id ``3.6``.

        Status of the port

    .. cpp:function:: OcaStatus AddToConnector(OcaONo Connector, OcaStreamConnectorPinIndex Index)

        This method has id ``3.6``.

        Adds the object number of the stream connector object to which this
        media port belongs, and specifies on what index of the stream
        connector this channel can be found. Return status indicates success
        of operation.

        :param OcaONo Connector: Input parameter.
        :param OcaStreamConnectorPinIndex Index: Input parameter.

    .. cpp:function:: OcaStatus GetConnectorPins(OcaMap<OcaONo, OcaStreamConnectorPinIndex> &ConnectorPins)

        This method has id ``3.5``.

        Gets the object number of the stream connector object to which this
        media port belongs, if any. If port does not belong to a stream
        connector, returns zero. Return status indicates success of operation.

        :param OcaMap<OcaONo, OcaStreamConnectorPinIndex> ConnectorPins: Output parameter.

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaNetworkSignalChannelID &IDAdvertised)

        This method has id ``3.1``.

        Gets the value of the IDAdvertised property. Return status indicates
        success of operation.

        :param OcaNetworkSignalChannelID IDAdvertised: Output parameter.

    .. cpp:function:: OcaStatus GetNetwork(OcaONo &Network)

        This method has id ``3.3``.

        Gets the object number of the stream network object to which this
        media port belongs. Return status indicates success of operation.

        :param OcaONo Network: Output parameter.

    .. cpp:function:: OcaStatus GetRemoteChannelID(OcaNetworkSignalChannelID &RemoteChannelID)

        This method has id ``3.8``.

        Gets the remote channel ID to which this channel is connected. Empty
        if the channel is not connected (at least not directly to another
        channel). For stream-oriented connection management this functionality
        is not used (i.e. the remote channel ID will always be empty).

        :param OcaNetworkSignalChannelID RemoteChannelID: Output parameter.

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        This method has id ``3.10``.

        Gets the value of the SourceOrSink property. Return status indicates
        success of operation.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Output parameter.

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkSignalChannelStatus &Status)

        This method has id ``3.11``.

        Gets the value of the Status property. Return status indicates success
        of operation.

        :param OcaNetworkSignalChannelStatus Status: Output parameter.

    .. cpp:function:: OcaStatus RemoveFromConnector(OcaONo Connector)

        This method has id ``3.7``.

        Removes this channel from the passed stream connector. Return status
        indicates success of operation.

        :param OcaONo Connector: Input parameter.

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaNetworkSignalChannelID IDAdvertised)

        This method has id ``3.2``.

        Sets the value of the IDAdvertised property. Return status indicates
        success of operation.

        :param OcaNetworkSignalChannelID IDAdvertised: Input parameter.

    .. cpp:function:: OcaStatus SetNetwork(OcaONo Network)

        This method has id ``3.4``.

        Sets the object number of the stream network object to which this
        media port belongs. Return status indicates success of operation. Only
        implemented for reconfigurable devices.

        :param OcaONo Network: Input parameter.

    .. cpp:function:: OcaStatus SetRemoteChannelID(OcaNetworkSignalChannelID RemoteChannelID)

        This method has id ``3.9``.

        Sets the remote channel ID to which this channel must be connected.
        Only used for channel-oriented connection management. For
        stream-oriented connection management this method is not used.
        Clearing the remote channel ID (i.e. tearing down the connection) can
        be done by passing an empty remote channel ID as parameter.

        :param OcaNetworkSignalChannelID RemoteChannelID: Input parameter.

