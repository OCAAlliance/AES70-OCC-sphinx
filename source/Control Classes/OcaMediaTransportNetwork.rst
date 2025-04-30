.. _ocamediatransportnetwork:

1.4.2  OcaMediaTransportNetwork
===============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaApplicationNetwork <ocaapplicationnetwork>` : :ref:`OcaMediaTransportNetwork <ocamediatransportnetwork>`

.. cpp:class:: OcaMediaTransportNetwork: OcaApplicationNetwork


    **Properties**:


    .. _ocamediatransportnetwork_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.4.2"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediatransportnetwork_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamediatransportnetwork_protocol:

    .. cpp:member:: OcaNetworkMediaProtocol Protocol

        Type of media transport protocol used by the network.

        This property has id ``3.1``.

    .. _ocamediatransportnetwork_ports:

    .. cpp:member:: OcaList<OcaPort> Ports

        The list of ports this network has. Note that these represent network
        channels of the media transport network. Each input port represents a
        source (transmit) network channel, each output port represents a sink
        (receive) network channel. Such network channels are directly linked to
        the ports, so the first input port represents the first source network
        channel, etc.

        This property has id ``3.2``.

    .. _ocamediatransportnetwork_maxsourceconnectors:

    .. cpp:member:: OcaUint16 MaxSourceConnectors

        The maximum number of source connectors this media transport network can
        have (read-only property).

        This property has id ``3.3``.

    .. _ocamediatransportnetwork_maxsinkconnectors:

    .. cpp:member:: OcaUint16 MaxSinkConnectors

        The maximum number of sink connectors this media transport network can
        have (read-only property).

        This property has id ``3.4``.

    .. _ocamediatransportnetwork_maxpinsperconnector:

    .. cpp:member:: OcaUint16 MaxPinsPerConnector

        The maximum number of pins (channels) in a connector that this network
        will support.

        This property has id ``3.5``.

    .. _ocamediatransportnetwork_maxportsperpin:

    .. cpp:member:: OcaUint16 MaxPortsPerPin

        The maximum number of ports per pin that this network will support.
        Value of zero indicates there is no specific limit.

        This property has id ``3.6``.

    .. _ocamediatransportnetwork_alignmentlevel:

    .. cpp:member:: OcaDBFS AlignmentLevel

        Default alignment level value for newly-created
        **OcaMedia{Source|Sink}Connector** elements. The min and max values of
        this property define respectively the lowest and highest alignment level
        values that may be specified when adding connectors to this network.

        This property has id ``3.7``.

    .. _ocamediatransportnetwork_alignmentgain:

    .. cpp:member:: OcaDB AlignmentGain

        Default value of AlignmentGain for newly-created OcaMediaSinkConnectors
        attached to this network. The min and max values of this property define
        respectively the lowest and highest alignment level values that may be
        specified when adding sink connectors to this network.

        This property has id ``3.8``.

    Properties inherited from :ref:`ocaapplicationnetwork`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaApplicationNetwork::ClassID <ocaapplicationnetwork_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaApplicationNetwork::ClassVersion <ocaapplicationnetwork_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaApplicationNetwork::Label <ocaapplicationnetwork_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaApplicationNetwork::Owner <ocaapplicationnetwork_owner>`

    - :cpp:texpr:`OcaApplicationNetworkServiceID` :ref:`OcaApplicationNetwork::ServiceID <ocaapplicationnetwork_serviceid>`

    - :cpp:texpr:`OcaList<OcaNetworkSystemInterfaceDescriptor>` :ref:`OcaApplicationNetwork::SystemInterfaces <ocaapplicationnetwork_systeminterfaces>`

    - :cpp:texpr:`OcaApplicationNetworkState` :ref:`OcaApplicationNetwork::State <ocaapplicationnetwork_state>`

    - :cpp:texpr:`OcaUint16` :ref:`OcaApplicationNetwork::ErrorCode <ocaapplicationnetwork_errorcode>`


    **Methods**:


    .. _ocamediatransportnetwork_getmediaprotocol:

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        Gets the network's Protocol property. Return status indicates whether
        the operation was successful.

        This method has id ``3.1``.

        - :cpp:expr:`Protocol`: Output parameter.


    .. _ocamediatransportnetwork_getports:

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        Gets the list of ports owned by the MediaTransportNetwork object
        (representing the source and sink network channels). The return value
        indicates whether the list was successfully retrieved.

        This method has id ``3.2``.

        - :cpp:expr:`OcaPorts`: Output parameter.


    .. _ocamediatransportnetwork_getportname:

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        Gets the name of the designated port. The return value indicates whether
        the name was successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Name`: Output parameter.


    .. _ocamediatransportnetwork_setportname:

    .. cpp:function:: OcaStatus SetPortName(OcaPortID PortID, OcaString Name)

        Sets the name of the designated port. The return value indicates whether
        the name was successfully set.

        This method has id ``3.4``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Name`: Input parameter.


    .. _ocamediatransportnetwork_getmaxsourceconnectors:

    .. cpp:function:: OcaStatus GetMaxSourceConnectors(OcaUint16 &MaxSourceConnectors)

        Gets the maximum number of source connectors this media transport
        network supports.

        This method has id ``3.5``.

        - :cpp:expr:`MaxSourceConnectors`: Output parameter.


    .. _ocamediatransportnetwork_getmaxsinkconnectors:

    .. cpp:function:: OcaStatus GetMaxSinkConnectors(OcaUint16 &MaxSinkConnectors)

        Gets the maximum number of source connectors this media transport
        network supports.

        This method has id ``3.6``.

        - :cpp:expr:`MaxSinkConnectors`: Output parameter.


    .. _ocamediatransportnetwork_getmaxpinsperconnector:

    .. cpp:function:: OcaStatus GetMaxPinsPerConnector(OcaUint16 &MaxPins)

        Gets the maximum number of ports per pin this media transport network
        supports.

        This method has id ``3.7``.

        - :cpp:expr:`MaxPins`: Output parameter.


    .. _ocamediatransportnetwork_getmaxportsperpin:

    .. cpp:function:: OcaStatus GetMaxPortsPerPin(OcaUint16 &MaxPins)

        Gets the maximum number of pins (channels) per connector this media
        transport network supports.

        This method has id ``3.8``.

        - :cpp:expr:`MaxPins`: Output parameter.


    .. _ocamediatransportnetwork_getsourceconnectors:

    .. cpp:function:: OcaStatus GetSourceConnectors(OcaList<OcaMediaSourceConnector> &Connectors)

        Gets the descriptors of all the source (output) connectors collected by
        this network object. Return status indicates success of the operation.

        This method has id ``3.9``.

        - :cpp:expr:`Connectors`: Output parameter.


    .. _ocamediatransportnetwork_getsourceconnector:

    .. cpp:function:: OcaStatus GetSourceConnector(OcaMediaConnectorID ID, OcaMediaSourceConnector &Connector)

        Retrieves the descriptor of a given source connector. Return status
        indicates the success of the operation.

        This method has id ``3.10``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Connector`: Output parameter.


    .. _ocamediatransportnetwork_getsinkconnectors:

    .. cpp:function:: OcaStatus GetSinkConnectors(OcaList<OcaMediaSinkConnector> &Connectors)

        Gets the descriptors of all the sink (output) connectors collected by
        this network object. Return status indicates success of the operation.

        This method has id ``3.11``.

        - :cpp:expr:`Connectors`: Output parameter.


    .. _ocamediatransportnetwork_getsinkconnector:

    .. cpp:function:: OcaStatus GetSinkConnector(OcaMediaConnectorID ID, OcaMediaSinkConnector &Connector)

        Retrieves the descriptor of a given sink connector. Return status
        indicates the success of the operation.

        This method has id ``3.12``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Connector`: Output parameter.


    .. _ocamediatransportnetwork_getconnectorsstatuses:

    .. cpp:function:: OcaStatus GetConnectorsStatuses(OcaList<OcaMediaConnectorStatus> &Statuses)

        Gets the status of all the source and sink connectors collected by this
        network object. Return status indicates success of the operation.

        This method has id ``3.13``.

        - :cpp:expr:`Statuses`: Output parameter.


    .. _ocamediatransportnetwork_getconnectorstatus:

    .. cpp:function:: OcaStatus GetConnectorStatus(OcaMediaConnectorID ConnectorID, OcaMediaConnectorStatus &Status)

        Gets the status of a single connector. Return status indicates success
        of the operation.

        This method has id ``3.14``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Status`: Output parameter.


    .. _ocamediatransportnetwork_addsourceconnector:

    .. cpp:function:: OcaStatus AddSourceConnector(OcaMediaSourceConnector Connector, OcaMediaConnectorState InitialStatus, OcaMediaSourceConnector &Connector_)

        Adds a source connector to this network. Parameters of the new connector
        are given in the Connector parameter; device returns the same parameter
        with the new connector ID filled in. If the new connector's
        AlignmentLevel property value is given as NaN, the value of this
        network's AlignmentLevel property will be used. Return status indicates
        the success of the operation.

        This method has id ``3.15``.

        - :cpp:expr:`Connector`: Input parameter.


        - :cpp:expr:`InitialStatus`: Input parameter.


        - :cpp:expr:`Connector_`: Output parameter.


    .. _ocamediatransportnetwork_addsinkconnector:

    .. cpp:function:: OcaStatus AddSinkConnector(OcaMediaConnectorStatus InitialStatus, OcaMediaSinkConnector Connector, OcaMediaSinkConnector &Connector_)

        Adds a sinkconnector to this network. Parameters of the new connector
        are given in the Connector parameter; device returns the same parameter
        with the new connector ID filled in. If the new connector's
        AlignmentLevel property value is given as NaN, the value of this
        network's AlignmentLevel property will be used. If the new connector's
        AlignmentGain property value is given as NaN, the value of this
        network's AlignmentGain property will be used. Return status indicates
        the success of the operation.

        This method has id ``3.16``.

        - :cpp:expr:`InitialStatus`: Input parameter.


        - :cpp:expr:`Connector`: Input parameter.


        - :cpp:expr:`Connector_`: Output parameter.


    .. _ocamediatransportnetwork_controlconnector:

    .. cpp:function:: OcaStatus ControlConnector(OcaMediaConnectorID ConnectorID, OcaMediaConnectorCommand Command)

        Change the state of a given connector. Return status indicates the
        success of the operation.

        This method has id ``3.17``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


    .. _ocamediatransportnetwork_setsourceconnectorpinmap:

    .. cpp:function:: OcaStatus SetSourceConnectorPinMap(OcaMediaConnectorID ConnectorID, OcaMap<OcaUint16, OcaPortID> ChannelPinMap)

        Sets a source connector's channel pin map. Return status indicates the
        success of the operation.

        This method has id ``3.18``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`ChannelPinMap`: Input parameter.


    .. _ocamediatransportnetwork_setsinkconnectorpinmap:

    .. cpp:function:: OcaStatus SetSinkConnectorPinMap(OcaMediaConnectorID ConnectorID, OcaMultiMap<OcaUint16, OcaPortID> ChannelPinMap)

        Sets a sink connector's channel pin map. Return status indicates the
        success of the operation.

        This method has id ``3.19``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`ChannelPinMap`: Input parameter.


    .. _ocamediatransportnetwork_setconnectorconnection:

    .. cpp:function:: OcaStatus SetConnectorConnection(OcaMediaConnectorID ConnectorID, OcaMediaConnection Connection)

        Sets a connector's **Connection** property. Return status indicates the
        success of the operation.

        This method has id ``3.20``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Connection`: Input parameter.


    .. _ocamediatransportnetwork_setconnectorcoding:

    .. cpp:function:: OcaStatus SetConnectorCoding(OcaMediaConnectorID ConnectorID, OcaMediaCoding Coding)

        Sets the Coding field of the connection descriptor of the referenced
        connector. Return status indicates the success of the operation.

        This method has id ``3.21``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Coding`: Input parameter.


    .. _ocamediatransportnetwork_setconnectoralignmentlevel:

    .. cpp:function:: OcaStatus SetConnectorAlignmentLevel(OcaMediaConnectorID ConnectorID, OcaDBFS Level)

        Sets the Alignment Level field of a connector. Value must be between the
        min and max values of the AlignmentLevel property of this network. A
        value of NaN will cause the current value of this network's
        AlignmentLevel property to be used. Return status indicates the success
        of the operation.

        This method has id ``3.22``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Level`: Input parameter.


    .. _ocamediatransportnetwork_setconnectoralignmentgain:

    .. cpp:function:: OcaStatus SetConnectorAlignmentGain(OcaMediaConnectorID ConnectorID, OcaDB Gain)

        For OcaMediaSinkConnectors only (not source). Sets the Alignment Gain
        field of the connection descriptor of the referenced connector. Value
        must be between the min and max values of the AlignmentGain property of
        this network. A value of NaN will cause the current value of the
        network's AlignmentGain property to be used. Return status indicates the
        success of the operation.

        This method has id ``3.23``.

        - :cpp:expr:`ConnectorID`: Input parameter.


        - :cpp:expr:`Gain`: Input parameter.


    .. _ocamediatransportnetwork_deleteconnector:

    .. cpp:function:: OcaStatus DeleteConnector(OcaMediaConnectorID ID)

        Deletes a connector from this network. Return status indicates the
        success of the operation.

        This method has id ``3.24``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportnetwork_getalignmentlevel:

    .. cpp:function:: OcaStatus GetAlignmentLevel(OcaDBFS &Level, OcaDBFS &MinLevel, OcaDBFS &MaxLevel)

        Gets the default, min, and max alignment levels for
        OcaMedia{Source|Sink}Connectors attached to this network. Return status
        indicates success of the operation.

        This method has id ``3.25``.

        - :cpp:expr:`Level`: Output parameter.


        - :cpp:expr:`MinLevel`: Output parameter.


        - :cpp:expr:`MaxLevel`: Output parameter.


    .. _ocamediatransportnetwork_getalignmentgain:

    .. cpp:function:: OcaStatus GetAlignmentGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the default, min, and max alignment gains for
        OcaMediaSinkConnectors attached to this network. Return status indicates
        success of the operation.

        This method has id ``3.26``.

        - :cpp:expr:`Gain`: Output parameter.


        - :cpp:expr:`minGain`: Output parameter.


        - :cpp:expr:`maxGain`: Output parameter.


    Methods inherited from :ref:`ocaapplicationnetwork`:

    - :ref:`OcaApplicationNetwork::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaApplicationNetwork::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaApplicationNetwork::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaApplicationNetwork::Unlock <ocaroot_unlock>`

    - :ref:`OcaApplicationNetwork::GetRole <ocaroot_getrole>`

    - :ref:`OcaApplicationNetwork::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaApplicationNetwork::GetLabel <ocaapplicationnetwork_getlabel>`

    - :ref:`OcaApplicationNetwork::SetLabel <ocaapplicationnetwork_setlabel>`

    - :ref:`OcaApplicationNetwork::GetOwner <ocaapplicationnetwork_getowner>`

    - :ref:`OcaApplicationNetwork::GetServiceID <ocaapplicationnetwork_getserviceid>`

    - :ref:`OcaApplicationNetwork::SetServiceID <ocaapplicationnetwork_setserviceid>`

    - :ref:`OcaApplicationNetwork::GetSystemInterfaces <ocaapplicationnetwork_getsysteminterfaces>`

    - :ref:`OcaApplicationNetwork::SetSystemInterfaces <ocaapplicationnetwork_setsysteminterfaces>`

    - :ref:`OcaApplicationNetwork::GetState <ocaapplicationnetwork_getstate>`

    - :ref:`OcaApplicationNetwork::GetErrorCode <ocaapplicationnetwork_geterrorcode>`

    - :ref:`OcaApplicationNetwork::Control <ocaapplicationnetwork_control>`

    - :ref:`OcaApplicationNetwork::GetPath <ocaapplicationnetwork_getpath>`


    **Events**:


    .. _ocamediatransportnetwork_sourceconnectorchanged:

    .. cpp:function:: void SourceConnectorChanged(OcaMediaSourceConnectorChangedEventData eventData)

        Event indicating that a media source connector has changed. The change
        type indicates if the connector was added, deleted or changed.

        This event has id ``3.1``.

    .. _ocamediatransportnetwork_sinkconnectorchanged:

    .. cpp:function:: void SinkConnectorChanged(OcaMediaSinkConnectorChangedEventData eventData)

        Event indicating that a media sink connector has changed. The change
        type indicates if the connector was added, deleted or changed.

        This event has id ``3.2``.

    .. _ocamediatransportnetwork_connectorstatuschanged:

    .. cpp:function:: void ConnectorStatusChanged(OcaMediaConnectorStatusChangedEventData eventData)

        Event indicating that the status of a source or sink connector has
        changed.

        This event has id ``3.3``.
