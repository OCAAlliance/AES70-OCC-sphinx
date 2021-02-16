.. _ocastreamconnector:

1.2.11  OcaStreamConnector
==========================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaStreamConnector: OcaAgent

    **DEPRECATED CLASS** *Replaced by the* **OcaMediaSinkConnector **
    *and* **OcaMediaSourceConnector ** *datatypes in version 3 of
    Connection Management (CM3)* Agent class for objects ("connectors")
    that allow connection of streams to the device. Streams may be single
    channels or multichannel groups. A connector is either a *source* or a
    *sink.* Sources are sometimes called "talkers". Sinks are sometimes
    called "listeners". Each connector links to zero or more **OcaStream**
    data objects. Each **OcaStream** object represents a signal flow to or
    from a local connector to a remote connector. The remote connector is
    usually, but not necessarily, in a different node. Each connector
    collects zero or more *signal channels* . A signal channel is an
    instance of **OcaNetworkSignalChannel.** Each signal channel exposes
    one media channel of the stream to the interior of the device. A
    signal channel therefore is a Worker that contains exactly one
    **OcaPort** data object. Each **OcaStreamConnector** object belongs to
    a particular instance of **OcaStreamNetwork** or a subclass of
    **OcaStreamNetwork** **.** Each **OcaStreamConnector** is linked to
    its network through the **Owner** property.
    
    - When a controller creates an **OcaStreamConnector** object
    dynamically, the controller must store the Object Number of the
    corresponding **OcaStreamNetwork** object in the **Owner** property.
    
    
    - Upon receiving the **Owner** property change, the
    **OcaStreamConnector** object must register itself with the given
    stream network object via some internal means.
    This class may be subclassed to support various network types.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        ID of this class

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Version number of this class

    .. cpp:member:: OcaStreamConnectorID IDAdvertised

        This property has id ``3.2``.

        Character name or binary identifier of this connector. This ID is
        advertised on the network to be found by other devices' discovery
        processes.

    .. cpp:member:: OcaONo OwnerNetwork

        This property has id ``3.1``.

        Object number of stream network object ( **OcaStreamNetwork** or one
        of its subclasses) to which this connector belongs. In reconfigurable
        devices, a controller that creates an **OcaStreamConnector** object
        must store the appropriate stream network object number into this
        property. It is assumed that, upon receiving a value into its
        **Owner** property, the terminus object will by internal means
        register itself with the identified stream network.

    .. cpp:member:: OcaMap<OcaStreamConnectorPinIndex, OcaONo> Pins

        This property has id ``3.5``.

        The map of connector pin indexes to
        **OcaNetworkSignalChannel[Source|Sink]** objects collected by this
        connector. The pin indexes are _fixed indexes_ 1 to n, where n is the
        number of channels the connector accommodates (determined when the
        connector is created). If a certain pin in the connector is currently
        not attached the OcaONo of that index is 0.

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        This property has id ``3.3``.

        Specifies whether this connector is for output (source) or input
        (sink) signal channels.

    .. cpp:member:: OcaStreamConnectorStatus Status

        This property has id ``3.6``.

        Status of this terminus.

    .. cpp:member:: OcaMap<OcaStreamIndex, OcaStream> Streams

        This property has id ``3.4``.

        The list of **OcaStream** data objects contained in (i.e. connected
        to) this connector.

    .. cpp:function:: OcaStatus ConnectStream(OcaStream Stream, OcaStreamIndex &Index)

        This method has id ``3.7``.

        Connects a stream to this connector. Return status indicates success
        of operation.

        :param OcaStream Stream: Input parameter.
        :param OcaStreamIndex Index: Output parameter.

    .. cpp:function:: OcaStatus DisconnectStream(OcaStreamIndex StreamID)

        This method has id ``3.8``.

        Disconnects a stream from this connector. Return status indicates
        success of operation.

        :param OcaStreamIndex StreamID: Input parameter.

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaStreamConnectorID &IDAdvertised)

        This method has id ``3.3``.

        Gets the value of the IDAdvertised property. Return status indicates
        success of operation.

        :param OcaStreamConnectorID IDAdvertised: Output parameter.

    .. cpp:function:: OcaStatus GetOwnerNetwork(OcaONo &Network)

        This method has id ``3.1``.

        Gets the object number of the **OcaStreamNetwork** object to which
        this connector belongs. Return status indicates success of operation.

        :param OcaONo Network: Output parameter.

    .. cpp:function:: OcaStatus GetPins(OcaMap<OcaStreamConnectorPinIndex, OcaONo> &Pins)

        This method has id ``3.10``.

        Gets the list of object numbers of **OcaNetworkSignalChannel** objects
        connected to this connector. Return status indicates success of
        operation.

        :param OcaMap<OcaStreamConnectorPinIndex, OcaONo> Pins: Output parameter.

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        This method has id ``3.5``.

        Gets the value of the SourceOrSink property. Return status indicates
        success of operation.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Output parameter.

    .. cpp:function:: OcaStatus GetStatus(OcaStreamConnectorStatus &Status)

        This method has id ``3.11``.

        Gets the value of the Status property. Return status indicates success
        of operation.

        :param OcaStreamConnectorStatus Status: Output parameter.

    .. cpp:function:: OcaStatus GetStreams(OcaMap<OcaStreamIndex, OcaStream> &Streams)

        This method has id ``3.9``.

        Gets the map of OcaStream items connected to this connector. Return
        status indicates success of operation.

        :param OcaMap<OcaStreamIndex, OcaStream> Streams: Output parameter.

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaStreamConnectorID IDAdvertised)

        This method has id ``3.4``.

        Sets the value of the IDAdvertised property. Return status indicates
        success of operation.

        :param OcaStreamConnectorID IDAdvertised: Input parameter.

    .. cpp:function:: OcaStatus SetOwnerNetwork(OcaONo Network)

        This method has id ``3.2``.

        Sets the object number of the **OcaStreamNetwork** object to which
        this connector belongs. Return status indicates success of operation.
        Only implemented for reconfigurable devices.

        :param OcaONo Network: Input parameter.

    .. cpp:function:: OcaStatus SetSourceOrSink(OcaNetworkMediaSourceOrSink SourceOrSink)

        This method has id ``3.6``.

        Sets the value of the SourceOrSink property. Return status indicates
        success of operation. Only implemented for reconfigurable devices.
        Note that this method can only be called when the SignalChannels
        property is empty, i.e. does not contain any actual channels.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Input parameter.

