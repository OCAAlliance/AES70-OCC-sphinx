.. _ocanetworksignalchannel:

1.1.6  OcaNetworkSignalChannel
==============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaNetworkSignalChannel <ocanetworksignalchannel>`

.. cpp:class:: OcaNetworkSignalChannel: OcaWorker

    **DEPRECATED CLASS** *Replaced by features of the* **OcaMediaSinkConnector
    ** *and* **OcaMediaSourceConnector ** *datatypes in version 3 of Connection
    Management (CM3)* Worker that allows connection of one or more internal
    signal paths to a network signal channel.

     - For stream-oriented media connection management such as used by AVB, this
       worker will be linked to an **OcaStreamConnector** object and to the
       appropriate **OcaStreamNetwork** object.

     - For channel-oriented media connection management, such as the Dante
       name-based routing mechanism, this worker will be linked only to the
       **OcaStreamNetwork** object.



    **Properties**:


    .. _ocanetworksignalchannel_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.6"

        ID of this class

        This property has id ``1.1``.

    .. _ocanetworksignalchannel_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Version number of this class

        This property has id ``1.2``.

    .. _ocanetworksignalchannel_connectorpins:

    .. cpp:member:: OcaMap<OcaONo, OcaStreamConnectorPinIndex> ConnectorPins

        Map of object numbers of **OcaStreamConnector** objects to
        **OcaStreamConnectorPinIndex** of these connectors. This map identifies
        which **OcaStreamConnector** objects contain this network signal
        channel, and indicates at what pin of the connector this channel is
        found. If the **OcaNetworkSignalChannel** object is not part of any
        **OcaStreamConnector** this map is empty. Note that
        **OcaNetworkSignalChannel** objects of type **Sink** cannot have more
        than one entry in the map, else it would implicitly perform mixing.
        **OcaNetworkSignalChannel** objects of type **Source** can have multiple
        entries in the map.

        This property has id ``3.3``.

    .. _ocanetworksignalchannel_idadvertised:

    .. cpp:member:: OcaNetworkSignalChannelID IDAdvertised

        Character name or binary identifier of the port that is advertised on
        the network to be found by other devices' discovery processes. Depending
        on the media transport architecture being used, this ID may be globally
        unique throughout the network, or only unique within the scope of the
        specific Network instance to which the port is attached.

        This property has id ``3.1``.

    .. _ocanetworksignalchannel_network:

    .. cpp:member:: OcaONo Network

        Object number of stream network object (**OcaStreamNetwork** or one of
        its subclasses) to which this signal channel belongs.

        This property has id ``3.2``.

    .. _ocanetworksignalchannel_remotechannelid:

    .. cpp:member:: OcaNetworkSignalChannelID RemoteChannelID

        External ID of ultimate source or destination of signal.

        This property has id ``3.4``.

    .. _ocanetworksignalchannel_sourceorsink:

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        Describes whether this signal channel is source (emits signals into the
        network) or sink (receives signals from the network). Sources are
        sometimes called "talkers", and sinks are sometimes called "listeners".

        This property has id ``3.5``.

    .. _ocanetworksignalchannel_status:

    .. cpp:member:: OcaNetworkSignalChannelStatus Status

        Status of the port

        This property has id ``3.6``.

    Properties inherited from :ref:`ocaworker`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaMap<OcaPortID, OcaPortClockMapEntry>` :ref:`OcaWorker::PortClockMap <ocaworker_portclockmap>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`


    **Methods**:


    .. _ocanetworksignalchannel_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaNetworkSignalChannelID &IDAdvertised)

        Gets the value of the IDAdvertised property. Return status indicates
        success of operation.

        This method has id ``3.1``.

        - :cpp:expr:`IDAdvertised`: Output parameter.


    .. _ocanetworksignalchannel_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaNetworkSignalChannelID IDAdvertised)

        Sets the value of the IDAdvertised property. Return status indicates
        success of operation.

        This method has id ``3.2``.

        - :cpp:expr:`IDAdvertised`: Input parameter.


    .. _ocanetworksignalchannel_getnetwork:

    .. cpp:function:: OcaStatus GetNetwork(OcaONo &Network)

        Gets the object number of the stream network object to which this media
        port belongs. Return status indicates success of operation.

        This method has id ``3.3``.

        - :cpp:expr:`Network`: Output parameter.


    .. _ocanetworksignalchannel_setnetwork:

    .. cpp:function:: OcaStatus SetNetwork(OcaONo Network)

        Sets the object number of the stream network object to which this media
        port belongs. Return status indicates success of operation. Only
        implemented for reconfigurable devices.

        This method has id ``3.4``.

        - :cpp:expr:`Network`: Input parameter.


    .. _ocanetworksignalchannel_getconnectorpins:

    .. cpp:function:: OcaStatus GetConnectorPins(OcaMap<OcaONo, OcaStreamConnectorPinIndex> &ConnectorPins)

        Gets the object number of the stream connector object to which this
        media port belongs, if any. If port does not belong to a stream
        connector, returns zero. Return status indicates success of operation.

        This method has id ``3.5``.

        - :cpp:expr:`ConnectorPins`: Output parameter.


    .. _ocanetworksignalchannel_addtoconnector:

    .. cpp:function:: OcaStatus AddToConnector(OcaONo Connector, OcaStreamConnectorPinIndex Index)

        Adds the object number of the stream connector object to which this
        media port belongs, and specifies on what index of the stream connector
        this channel can be found. Return status indicates success of operation.

        This method has id ``3.6``.

        - :cpp:expr:`Connector`: Input parameter.


        - :cpp:expr:`Index`: Input parameter.


    .. _ocanetworksignalchannel_removefromconnector:

    .. cpp:function:: OcaStatus RemoveFromConnector(OcaONo Connector)

        Removes this channel from the passed stream connector. Return status
        indicates success of operation.

        This method has id ``3.7``.

        - :cpp:expr:`Connector`: Input parameter.


    .. _ocanetworksignalchannel_getremotechannelid:

    .. cpp:function:: OcaStatus GetRemoteChannelID(OcaNetworkSignalChannelID &RemoteChannelID)

        Gets the remote channel ID to which this channel is connected. Empty if
        the channel is not connected (at least not directly to another channel).
        For stream-oriented connection management this functionality is not used
        (i.e. the remote channel ID will always be empty).

        This method has id ``3.8``.

        - :cpp:expr:`RemoteChannelID`: Output parameter.


    .. _ocanetworksignalchannel_setremotechannelid:

    .. cpp:function:: OcaStatus SetRemoteChannelID(OcaNetworkSignalChannelID RemoteChannelID)

        Sets the remote channel ID to which this channel must be connected. Only
        used for channel-oriented connection management. For stream-oriented
        connection management this method is not used. Clearing the remote
        channel ID (i.e. tearing down the connection) can be done by passing an
        empty remote channel ID as parameter.

        This method has id ``3.9``.

        - :cpp:expr:`RemoteChannelID`: Input parameter.


    .. _ocanetworksignalchannel_getsourceorsink:

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        Gets the value of the SourceOrSink property. Return status indicates
        success of operation.

        This method has id ``3.10``.

        - :cpp:expr:`SourceOrSink`: Output parameter.


    .. _ocanetworksignalchannel_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkSignalChannelStatus &Status)

        Gets the value of the Status property. Return status indicates success
        of operation.

        This method has id ``3.11``.

        - :cpp:expr:`Status`: Output parameter.


    Methods inherited from :ref:`ocaworker`:

    - :ref:`OcaWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaWorker::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaWorker::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaWorker::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaWorker::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaWorker::GetPath <ocaworker_getpath>`

    - :ref:`OcaWorker::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaWorker::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaWorker::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaWorker::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaWorker::SetPortName <ocaworker_setportname>`

