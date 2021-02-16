.. _ocamediatransportnetwork:

1.4.2  OcaMediaTransportNetwork
===============================

Extends :ref:`OcaApplicationNetwork <ocaapplicationnetwork>`.

.. cpp:class:: OcaMediaTransportNetwork: OcaApplicationNetwork


    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaNetworkMediaProtocol Protocol

        This property has id ``3.1``.

        Type of media transport protocol used by the network.

    .. cpp:member:: OcaList<OcaPort> Ports

        This property has id ``3.2``.

        The list of ports this network has. Note that these represent network
        channels of the media transport network. Each input port represents a
        source (transmit) network channel, each output port represents a sink
        (receive) network channel. Such network channels are directly linked
        to the ports, so the first input port represents the first source
        network channel, etc.

    .. cpp:member:: OcaUint16 MaxSourceConnectors

        This property has id ``3.3``.

        The maximum number of source connectors this media transport network
        can have (read-only property).

    .. cpp:member:: OcaUint16 MaxSinkConnectors

        This property has id ``3.4``.

        The maximum number of sink connectors this media transport network can
        have (read-only property).

    .. cpp:member:: OcaUint16 MaxPinsPerConnector

        This property has id ``3.5``.

        The maximum number of pins (channels) in a connector that this network
        will support.

    .. cpp:member:: OcaUint16 MaxPortsPerPin

        This property has id ``3.6``.

        The maximum number of ports per pin that this network will support.
        Value of zero indicates there is no specific limit.

    .. cpp:member:: OcaDBFS AlignmentLevel

        This property has id ``3.7``.

        Default alignment level value for newly-created
        **OcaMedia{Source|Sink}Connector** elements. The min and max values of
        this property define respectively the lowest and highest alignment
        level values that may be specified when adding connectors to this
        network.

    .. cpp:member:: OcaDB AlignmentGain

        This property has id ``3.8``.

        Default value of AlignmentGain for newly-created
        OcaMediaSinkConnectors attached to this network. The min and max
        values of this property define respectively the lowest and highest
        alignment level values that may be specified when adding sink
        connectors to this network.

    .. cpp:member:: OcaList<OcaMediaSinkConnector> SinkConnectors

        This property has id ``3.0``.

        The list of sink connectors this network has. This is a private
        property, so it does not generate property-change events. It may be
        accessed by the relevant methods.

    .. cpp:member:: OcaList<OcaMediaSourceConnector> SourceConnectors

        This property has id ``3.0``.

        The list of source connectors this network has. This is a private
        property, so it does not generate property-change events. It may be
        accessed by the relevant methods.

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        This method has id ``3.1``.

        Gets the network's Protocol property. Return status indicates whether
        the operation was successful.

        :param OcaNetworkMediaProtocol Protocol: Output parameter.

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        This method has id ``3.2``.

        Gets the list of ports owned by the MediaTransportNetwork object
        (representing the source and sink network channels). The return value
        indicates whether the list was successfully retrieved.

        :param OcaList<OcaPort> OcaPorts: Output parameter.

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        This method has id ``3.3``.

        Gets the name of the designated port. The return value indicates
        whether the name was successfully retrieved.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Output parameter.

    .. cpp:function:: OcaStatus SetPortName(OcaPortID PortID, OcaString Name)

        This method has id ``3.4``.

        Sets the name of the designated port. The return value indicates
        whether the name was successfully set.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Input parameter.

    .. cpp:function:: OcaStatus GetMaxSourceConnectors(OcaUint16 &MaxSourceConnectors)

        This method has id ``3.5``.

        Gets the maximum number of source connectors this media transport
        network supports.

        :param OcaUint16 MaxSourceConnectors: Output parameter.

    .. cpp:function:: OcaStatus GetMaxSinkConnectors(OcaUint16 &MaxSinkConnectors)

        This method has id ``3.6``.

        Gets the maximum number of source connectors this media transport
        network supports.

        :param OcaUint16 MaxSinkConnectors: Output parameter.

    .. cpp:function:: OcaStatus GetMaxPinsPerConnector(OcaUint16 &MaxPins)

        This method has id ``3.7``.

        Gets the maximum number of ports per pin this media transport network
        supports.

        :param OcaUint16 MaxPins: Output parameter.

    .. cpp:function:: OcaStatus GetMaxPortsPerPin(OcaUint16 &MaxPins)

        This method has id ``3.8``.

        Gets the maximum number of pins (channels) per connector this media
        transport network supports.

        :param OcaUint16 MaxPins: Output parameter.

    .. cpp:function:: OcaStatus GetSourceConnectors(OcaList<OcaMediaSourceConnector> &Connectors)

        This method has id ``3.9``.

        Gets the descriptors of all the source (output) connectors collected
        by this network object. Return status indicates success of the
        operation.

        :param OcaList<OcaMediaSourceConnector> Connectors: Output parameter.

    .. cpp:function:: OcaStatus GetSourceConnector(OcaMediaConnectorID ID, OcaMediaSourceConnector &Connector)

        This method has id ``3.10``.

        Retrieves the descriptor of a given source connector. Return status
        indicates the success of the operation.

        :param OcaMediaConnectorID ID: Input parameter.
        :param OcaMediaSourceConnector Connector: Output parameter.

    .. cpp:function:: OcaStatus GetSinkConnectors(OcaList<OcaMediaSinkConnector> &Connectors)

        This method has id ``3.11``.

        Gets the descriptors of all the sink (output) connectors collected by
        this network object. Return status indicates success of the operation.

        :param OcaList<OcaMediaSinkConnector> Connectors: Output parameter.

    .. cpp:function:: OcaStatus GetSinkConnector(OcaMediaConnectorID ID, OcaMediaSinkConnector &Connector)

        This method has id ``3.12``.

        Retrieves the descriptor of a given sink connector. Return status
        indicates the success of the operation.

        :param OcaMediaConnectorID ID: Input parameter.
        :param OcaMediaSinkConnector Connector: Output parameter.

    .. cpp:function:: OcaStatus GetConnectorsStatuses(OcaList<OcaMediaConnectorStatus> &Statuses)

        This method has id ``3.13``.

        Gets the status of all the source and sink connectors collected by
        this network object. Return status indicates success of the operation.

        :param OcaList<OcaMediaConnectorStatus> Statuses: Output parameter.

    .. cpp:function:: OcaStatus GetConnectorStatus(OcaMediaConnectorID ConnectorID, OcaMediaConnectorStatus &Status)

        This method has id ``3.14``.

        Gets the status of a single connector. Return status indicates success
        of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMediaConnectorStatus Status: Output parameter.

    .. cpp:function:: OcaStatus AddSourceConnector(OcaMediaSourceConnector Connector, OcaMediaConnectorState InitialStatus, OcaMediaSourceConnector &Connector_)

        This method has id ``3.15``.

        Adds a source connector to this network. Parameters of the new
        connector are given in the Connector parameter; device returns the
        same parameter with the new connector ID filled in. If the new
        connector's AlignmentLevel property value is given as NaN, the value
        of this network's AlignmentLevel property will be used. Return status
        indicates the success of the operation.

        :param OcaMediaSourceConnector Connector: Input parameter.
        :param OcaMediaConnectorState InitialStatus: Input parameter.
        :param OcaMediaSourceConnector Connector_: Output parameter.

    .. cpp:function:: OcaStatus AddSinkConnector(OcaMediaConnectorStatus InitialStatus, OcaMediaSinkConnector Connector, OcaMediaSinkConnector &Connector_)

        This method has id ``3.16``.

        Adds a sinkconnector to this network. Parameters of the new connector
        are given in the Connector parameter; device returns the same
        parameter with the new connector ID filled in. If the new connector's
        AlignmentLevel property value is given as NaN, the value of this
        network's AlignmentLevel property will be used. If the new connector's
        AlignmentGain property value is given as NaN, the value of this
        network's AlignmentGain property will be used. Return status indicates
        the success of the operation.

        :param OcaMediaConnectorStatus InitialStatus: Input parameter.
        :param OcaMediaSinkConnector Connector: Input parameter.
        :param OcaMediaSinkConnector Connector_: Output parameter.

    .. cpp:function:: OcaStatus ControlConnector(OcaMediaConnectorID ConnectorID, OcaMediaConnectorCommand Command)

        This method has id ``3.17``.

        Change the state of a given connector. Return status indicates the
        success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMediaConnectorCommand Command: Input parameter.

    .. cpp:function:: OcaStatus SetSourceConnectorPinMap(OcaMediaConnectorID ConnectorID, OcaMap<OcaUint16, OcaPortID> ChannelPinMap)

        This method has id ``3.18``.

        Sets a source connector's channel pin map. Return status indicates the
        success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMap<OcaUint16, OcaPortID> ChannelPinMap: Input parameter.

    .. cpp:function:: OcaStatus SetSinkConnectorPinMap(OcaMediaConnectorID ConnectorID, OcaMultiMap<OcaUint16, OcaPortID> ChannelPinMap)

        This method has id ``3.19``.

        Sets a sink connector's channel pin map. Return status indicates the
        success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMultiMap<OcaUint16, OcaPortID> ChannelPinMap: Input parameter.

    .. cpp:function:: OcaStatus SetConnectorConnection(OcaMediaConnectorID ConnectorID, OcaMediaConnection Connection)

        This method has id ``3.20``.

        Sets a connector's **Connection** property. Return status indicates
        the success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMediaConnection Connection: Input parameter.

    .. cpp:function:: OcaStatus SetConnectorCoding(OcaMediaConnectorID ConnectorID, OcaMediaCoding Coding)

        This method has id ``3.21``.

        Sets the Coding field of the connection descriptor of the referenced
        connector. Return status indicates the success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaMediaCoding Coding: Input parameter.

    .. cpp:function:: OcaStatus SetConnectorAlignmentLevel(OcaMediaConnectorID ConnectorID, OcaDBFS Level)

        This method has id ``3.22``.

        Sets the Alignment Level field of a connector. Value must be between
        the min and max values of the AlignmentLevel property of this network.
        A value of NaN will cause the current value of this network's
        AlignmentLevel property to be used. Return status indicates the
        success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaDBFS Level: Input parameter.

    .. cpp:function:: OcaStatus SetConnectorAlignmentGain(OcaMediaConnectorID ConnectorID, OcaDB Gain)

        This method has id ``3.23``.

        For OcaMediaSinkConnectors only (not source). Sets the Alignment Gain
        field of the connection descriptor of the referenced connector. Value
        must be between the min and max values of the AlignmentGain property
        of this network. A value of NaN will cause the current value of the
        network's AlignmentGain property to be used. Return status indicates
        the success of the operation.

        :param OcaMediaConnectorID ConnectorID: Input parameter.
        :param OcaDB Gain: Input parameter.

    .. cpp:function:: OcaStatus DeleteConnector(OcaMediaConnectorID ID)

        This method has id ``3.24``.

        Deletes a connector from this network. Return status indicates the
        success of the operation.

        :param OcaMediaConnectorID ID: Input parameter.

    .. cpp:function:: OcaStatus GetAlignmentLevel(OcaDBFS &Level, OcaDBFS &MinLevel, OcaDBFS &MaxLevel)

        This method has id ``3.25``.

        Gets the default, min, and max alignment levels for
        OcaMedia{Source|Sink}Connectors attached to this network. Return
        status indicates success of the operation.

        :param OcaDBFS Level: Output parameter.
        :param OcaDBFS MinLevel: Output parameter.
        :param OcaDBFS MaxLevel: Output parameter.

    .. cpp:function:: OcaStatus GetAlignmentGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``3.26``.

        Gets the default, min, and max alignment gains for
        OcaMediaSinkConnectors attached to this network. Return status
        indicates success of the operation.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

