************************
Deprecated CM2 Datatypes
************************

.. _OcaNetworkLinkType:

OcaNetworkLinkType
==================

.. cpp:enum:: OcaNetworkLinkType : uint8_t

    Types of layer 2 networks.

    .. cpp:enumerator:: None = 0

        No network

    .. cpp:enumerator:: EthernetWired = 1

        Wired Ethernet

    .. cpp:enumerator:: EthernetWireless = 2

        Wireless Ethernet

    .. cpp:enumerator:: USB = 3

        USB

    .. cpp:enumerator:: SerialP2P = 4

        Low-speed serial point-to-point

.. _OcaNetworkHostID:

OcaNetworkHostID
================

.. cpp:type:: OcaNetworkHostID = OcaBlob

    ID (name or address) of network host found by the discovery process.

.. _OcaNetworkNodeID:

OcaNetworkNodeID
================

.. cpp:type:: OcaNetworkNodeID = OcaBlob

    ID (name or GUID) of network node. There may be one or more nodes per host.
    Nodes offer media network services, and are what is discovered by discovery
    processes. Each instance of **OcaNetwork** (or one of its subclasses) is a
    node.

.. _OcaStreamConnectorPinIndex:

OcaStreamConnectorPinIndex
==========================

.. cpp:type:: OcaStreamConnectorPinIndex = OcaUint16

    An index of a pin of an OcaNetworkSignalChannel object. This is a CM2 class,
    deprecated as of OCA 1.4 .

.. _OcaNetworkSystemInterfaceID:

OcaNetworkSystemInterfaceID
===========================

.. cpp:struct:: OcaNetworkSystemInterfaceID

    ID of a system interface used by a network. Format is data network type
    dependent.

    .. cpp:member:: OcaBlob SystemInterfaceHandle

        Operating system handle for the interface the network uses to do I/O.

    .. cpp:member:: OcaNetworkAddress MyNetworkAddress

        The data network address that corresponds to this system interface.

.. _OcaNetworkSignalChannelID:

OcaNetworkSignalChannelID
=========================

.. cpp:type:: OcaNetworkSignalChannelID = OcaBlob

    External ID of a signal channel. Name or number, depending on transport
    architecture being used. **This datatype is deprecated as of OCA 1.4**

.. _OcaNetworkStatistics:

OcaNetworkStatistics
====================

.. cpp:struct:: OcaNetworkStatistics

    Historical statistics of the network.

    .. cpp:member:: OcaUint32 rxPacketErrors

        The number of receiver packet errors.

    .. cpp:member:: OcaUint32 txPacketErrors

        The number of transmitter packet errors.

.. _OcaStreamConnectorID:

OcaStreamConnectorID
====================

.. cpp:type:: OcaStreamConnectorID = OcaBlob

    Public ID of a network stream connector. Name or number, depending on
    transport architecture being used.

.. _OcaStream:

OcaStream
=========

.. cpp:struct:: OcaStream

    A single-channel or multichannel signal flow between a local stream
    connector (i.e. **OcaStreamConnector** instance) of an **OcaStreamNetwork**
    object in this node and another ("remote") stream connector. Normally, the
    remote stream connector is in another node. Each stream is unidirectional.
    With respect to the **OcaStreamNetwork** object in question, a stream is
    either:

     - *Outbound: * A signal flow from an output connector port in the
       **OcaStreamNetwork** object to an external destination; or

     - *Inbound: * A signal flow from an external source to an *input* connector
       in the **OcaStreamNetwork** object.


    An **OcaStream** object may represent either a unicast or a multicast
    stream. Any given **OcaStreamConnector** object may support multiple
    outbound flows, but not multiple inbound flows.

    .. cpp:member:: OcaUint16 ErrorNumber

        Index of most recent error encountered.

    .. cpp:member:: OcaStreamID IDAdvertised

        Public identifier of this stream.

    .. cpp:member:: OcaStreamIndex Index

        Index of this stream. Unique within owner OcaNetwork2 object.

    .. cpp:member:: OcaString Label

        Arbitrary user-settable name for this stream.

    .. cpp:member:: OcaONo LocalConnectorONo

        Object number of **OcaStreamConnector** object to which this stream is
        connected. A value of zero means the stream is not connected to any
        connector in this device.

    .. cpp:member:: OcaUint16 Priority

        Traffic priority of stream. Values are network implementation dependant.

    .. cpp:member:: OcaStreamConnectorIdentification RemoteConnectorIdentification

        Full identifier of the connector at the far end of this stream.

    .. cpp:member:: OcaBoolean Secure

        True if and only if connection is secure.

    .. cpp:member:: OcaStreamStatus Status

        Current status of the stream.

    .. cpp:member:: OcaStreamParameters StreamParameters

        Stream parameters (encoding, sampling, etc). Details TBD

    .. cpp:member:: OcaStreamType StreamType

        Unicast or multicast

.. _OcaNetworkControlProtocol:

OcaNetworkControlProtocol
=========================

.. cpp:enum:: OcaNetworkControlProtocol : uint8_t

    Network control protocols available.

    .. cpp:enumerator:: None = 0

        No control protocol - the network does not do control.

    .. cpp:enumerator:: OCP01 = 1

        OCP.1 - OCA protocol for TCP/IP networks

    .. cpp:enumerator:: OCP02 = 2

        OCP.2 - OCA protocol for USB links.

    .. cpp:enumerator:: OCP03 = 3

        OCP.3 - Character XML or JSON (tbd) version of OCA protocol, for serial
        links and other purposes.

.. _OcaStreamID:

OcaStreamID
===========

.. cpp:type:: OcaStreamID = OcaBlob

    Public ID of a stream. Name or number, depending on transport architecture
    being used.

.. _OcaStreamConnectorIdentification:

OcaStreamConnectorIdentification
================================

.. cpp:struct:: OcaStreamConnectorIdentification

    A signal source or sink connector at the far end of a stream - normally, in
    another device. Not all of the fields of this datatype need be used. The
    fields used will depend on remote device type, media transport network type,
    and media transport implementation. Normal usage scenarios are:

     - **Unicast input or output**: The **OcaStream** object is instantiated in
       an **OcaStreamConnector** object in the local device, and it links to an
       **OcaStreamConnector** object in a remote device.

     - **Multicast input** : The **OcaStream** object is instantiated in an
       **OcaStreamConnector** object in the local device, and, it may or may not
       link to an **OcaStreamConnector** object in a remote device.

     - **Multicast output** : The **OcaStream** object is instantiated in an
       **OcaStreamConnector** object in the local device, but in this case does
       not link to any specific remote connector object.



    .. cpp:member:: OcaNetworkHostID HostID

        Public name or binary ID of host in which this connector resides.

    .. cpp:member:: OcaNetworkAddress NetworkAddress

        Network address of host in which this connector resides.

    .. cpp:member:: OcaNetworkNodeID NodeID

        Public name or binary ID of node within the host to which this connector
        belongs.

    .. cpp:member:: OcaStreamConnectorID StreamConnectorID

        Public name or binary ID of this stream connector.

.. _OcaStreamIndex:

OcaStreamIndex
==============

.. cpp:type:: OcaStreamIndex = OcaUint16

    Internal handle of a stream.

.. _OcaNetworkStatus:

OcaNetworkStatus
================

.. cpp:enum:: OcaNetworkStatus : uint8_t

    Network status enum.

    .. cpp:enumerator:: Unknown = 0

        Status is not known for some reason.

    .. cpp:enumerator:: Ready = 1

        Network is ready for data transfer.

    .. cpp:enumerator:: StartingUp = 2

        Network is starting up.

    .. cpp:enumerator:: Stopped = 3

        Network has been stopped by a call to the Stop() method. All media
        connections and/or control sessions have been closed.

.. _OcaStreamConnectorStatus:

OcaStreamConnectorStatus
========================

.. cpp:enum:: OcaStreamConnectorStatus : uint8_t

    Status options for a stream connector.

    .. cpp:enumerator:: NotAvailable = 0

        Connector is not ready to transfer data.

    .. cpp:enumerator:: Idle = 1

        Connector is ready for data transfer but is not connected to any
        streams.

    .. cpp:enumerator:: Connected = 2

        Connector is connected to at least one stream.

    .. cpp:enumerator:: Paused = 3

        Connector is connected to at least one stream but data transfer has been
        halted by controller request.

.. _OcaNetworkSignalChannelStatus:

OcaNetworkSignalChannelStatus
=============================

.. cpp:enum:: OcaNetworkSignalChannelStatus : uint8_t

    Status options for a stream.

    .. cpp:enumerator:: NotConnected = 0

        Channel is not ready to transfer data.

    .. cpp:enumerator:: Connected = 1

        Channel is ready for data transfer.

    .. cpp:enumerator:: Muted = 2

        Channel is set up, but data transfer has been halted.

.. _OcaNetworkMediaSourceOrSink:

OcaNetworkMediaSourceOrSink
===========================

.. cpp:enum:: OcaNetworkMediaSourceOrSink : uint8_t

    enum that describes whether a port is a source (= sends program into the
    network; "talker") or sink (=receives program from the network; "listener")

    .. cpp:enumerator:: None = 0

        Port direction is undefined.

    .. cpp:enumerator:: Source = 1

        Port is source (= talker)

    .. cpp:enumerator:: Sink = 2

        Port is sink (=listener)

.. _OcaStreamType:

OcaStreamType
=============

.. cpp:enum:: OcaStreamType : uint8_t

    Type of media endpoint: unicast or multicast.

    .. cpp:enumerator:: None = 0

        Unknown media endpoint type.

    .. cpp:enumerator:: Unicast = 1

        Unicast stream.

    .. cpp:enumerator:: Multicast = 2

        Multicast stream

.. _OcaStreamStatus:

OcaStreamStatus
===============

.. cpp:enum:: OcaStreamStatus : uint8_t

    Status options for a stream.

    .. cpp:enumerator:: NotConnected = 0

        Connection is not ready to transfer data.

    .. cpp:enumerator:: Connected = 1

        Connection is ready for data transfer.

    .. cpp:enumerator:: Paused = 2

        Connection is set up, but data transfer has been halted.

