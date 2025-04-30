*******************************
Media Stream Endpoint Datatypes
*******************************

.. _OcaMediaStreamEndpointID:

OcaMediaStreamEndpointID
========================

.. cpp:type:: OcaMediaStreamEndpointID = OcaUint32

    Internal ID of a media stream endpoint

.. _OcaMediaStreamEndpoint:

OcaMediaStreamEndpoint
======================

.. cpp:struct:: OcaMediaStreamEndpoint

    Media stream endpoint descriptor. Collected by
    **OcaMediaTransportApplication**.

    .. cpp:member:: OcaMediaStreamEndpointID IDInternal

        Internal ID.

    .. cpp:member:: OcaBlob IDExternal

        Public identifier of endpoint. May be advertised on the network.

    .. cpp:member:: OcaIODirection Direction

        Input or output (input ``->`` samples flow into endpoint from network,
        ``output->samples`` flow out of endpoint into network)

    .. cpp:member:: OcaString UserLabel

        Arbitrary user-settable label for endpoint.

    .. cpp:member:: OcaList<OcaID16> NetworkAssignmentIDs

        ID(s) of the Network Assignment(s) this endpoint is using.

    .. cpp:member:: OcaList<OcaID16> StreamModeCapabilityIDs

        Media stream mode capabilities of this endpoint. List of indexes into
        **OcaMediaTransportApplication.MediaStreamModeCapabilities**.

    .. cpp:member:: OcaONo ClockONo

        ONo of **OcaMediaClock3** media clock for this endpoint.

    .. cpp:member:: OcaBoolean ChannelMapDynamic

        TRUE if and only if channel map may be modified at runtime.

    .. cpp:member:: OcaMultiMap<OcaUint16, OcaPortID> ChannelMap

        Map of this endpoint's signal channels to OCA Ports of the owning
        **OcaMediaTransportApplication** object. Each input endpoint channel may
        be mapped to zero or more **output** Ports; each output endpoint channel
        may be mapped to at most one **input** Port.

    .. cpp:member:: OcaDBFS AlignmentLevel

        Alignment Level of the endpoint. The dBFS value is referenced to the
        endpoint's fullscale value, not to Device's internal fullscale value.

    .. cpp:member:: OcaMediaStreamMode CurrentStreamMode

        Stream mode of current connection. If there is a no current connection,
        value is undefined.

    .. cpp:member:: OcaSecurityType SecurityType

        Security type of this endpoint, if any.

    .. cpp:member:: OcaMediaStreamCastMode StreamCastMode

        Unicast or multicast

    .. cpp:member:: OcaAdaptationData AdaptationData

        Adaptation-specific connection data, e.g. IP addresses and ports of
        input and output endpoints. Specific media transport adaptations will
        define the fine-structure of this **OcaBlob**.

    .. cpp:member:: OcaID16 RedundantSetID

        ID of redundant set this endpoint belongs to. Unique within
        **OcaMediaTransportApplication** instance.

.. _OcaMediaStreamEndpointStatus:

OcaMediaStreamEndpointStatus
============================

.. cpp:struct:: OcaMediaStreamEndpointStatus

    Current status of a media stream endpoint.

    .. cpp:member:: OcaMediaStreamEndpointState State

        Endpoint state

    .. cpp:member:: OcaUint16 ErrorCode

        Indicates what type of error the endpoint has encountered. Irrelevant if
        State is not **Fault**.

.. _OcaMediaStreamEndpointState:

OcaMediaStreamEndpointState
===========================

.. cpp:enum:: OcaMediaStreamEndpointState : uint8_t

    State of a stream endpoint.

    .. cpp:enumerator:: Unknown = 0

        State of endpoint is unknown.

    .. cpp:enumerator:: NotReady = 1

        Endpoint is not ready for media transport.

    .. cpp:enumerator:: Ready = 2

        Endpoint is ready for media transport but is not connected to a stream.

    .. cpp:enumerator:: Connected = 3

        Endpoint has a connection but media stream data is not flowing.

    .. cpp:enumerator:: Running = 4

        Endpoint has a connection and media stream data is flowing.

    .. cpp:enumerator:: ErrorHalt = 5

        Data transfer has been halted due to errors.

.. _OcaMediaStreamEndpointCommand:

OcaMediaStreamEndpointCommand
=============================

.. cpp:enum:: OcaMediaStreamEndpointCommand : uint8_t

    Command values for
    **OcaMediaTransportApplication.ApplyEndpointCommand(...)**

    .. cpp:enumerator:: None = 0

        No-op. State shall not be changed.

    .. cpp:enumerator:: SetReady = 1

        Prepare Endpoint for connection. If the command succeeds, the resulting
        state shall be **Ready**.

    .. cpp:enumerator:: Connect = 2

        Connect to a stream. If the command succeeds, the resulting state shall
        be **Connected.**

    .. cpp:enumerator:: ConnectAndStart = 3

        Connect to a stream. If the command succeeds, the resulting state shall
        be **Running**.

    .. cpp:enumerator:: Disconnect = 4

        Disconnect from a stream. If the command succeeds, the resulting state
        shall be **Ready**.

    .. cpp:enumerator:: StopAndDisconnect = 5

        Stop media data transfer and disconnect from a running stream. If the
        command succeeds, the resulting state shall be **Ready**.

    .. cpp:enumerator:: Start = 6

        Commence media data transfer. If the command succeeds, the resulting
        state shall be **Running.**

    .. cpp:enumerator:: Stop = 7

        Stop media data transfer, but preserve the connection. If the command
        succeeds, the resulting state shall be **Connected**.

.. _OcaMediaStreamCastMode:

OcaMediaStreamCastMode
======================

.. cpp:enum:: OcaMediaStreamCastMode : uint8_t

    Transmission mode: unicast or multicast

    .. cpp:enumerator:: Unknown = 0

        Unknown mode

    .. cpp:enumerator:: Unicast = 1

        Unicast mode

    .. cpp:enumerator:: Multicast = 2

        Multicast mode

