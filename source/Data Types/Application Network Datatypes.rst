*****************************
Application Network Datatypes
*****************************

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
.. _OcaApplicationNetworkServiceID:

OcaApplicationNetworkServiceID
==============================

.. cpp:type:: OcaApplicationNetworkServiceID = OcaBlob

    Generic host ID.
.. _OcaNetworkSystemInterfaceDescriptor:

OcaNetworkSystemInterfaceDescriptor
===================================

.. cpp:struct:: OcaNetworkSystemInterfaceDescriptor
    
    Descriptor of a system interface used by a network. Format is data
    network type dependent.

    .. cpp:member:: OcaBlob SystemInterfaceParameters

        Parameters for the operating system interface the network uses to do
        I/O.

    .. cpp:member:: OcaNetworkAddress MyNetworkAddress

        The data network address that corresponds to this system interface.


OCP.1 Encoding
--------------

================================== ========== ===========
Field                              Basic type Byte length
================================== ========== ===========
SystemInterfaceParameters.DataSize OcaUint16  2          
SystemInterfaceParameters.Data     OcaUint8   1 * Count  
MyNetworkAddress.Value.DataSize    OcaUint16  2          
MyNetworkAddress.Value.Data        OcaUint8   1 * Count  
================================== ========== ===========


.. _OcaApplicationNetworkState:

OcaApplicationNetworkState
==========================

.. cpp:enum:: OcaApplicationNetworkState : uint8_t

    Network states.

    .. cpp:enumerator:: Unknown = 0

        State is not known.
    .. cpp:enumerator:: NotReady = 1

        Application network is not connected to host data network and is
        therefore not ready for connection establishng or application data
        transfer.
    .. cpp:enumerator:: Readying = 2

        Application network is in the process of connecting to the host data
        network and is therefore not ready for connection establishing or
        application data transfer.
    .. cpp:enumerator:: Ready = 3

        Application network is connected to host data network and is ready for
        connection establishing and application data transfer.
    .. cpp:enumerator:: Running = 4

        Application network is connected to host data network and is executing
        connection establishment and application data transfer.
    .. cpp:enumerator:: Paused = 5

        All application data transfer is paused, but connections are still in
        place.
    .. cpp:enumerator:: Stopping = 6

        Network is in the process of stopping all media application data
        transport activity and is deleting all media transport connections.
    .. cpp:enumerator:: Stopped = 7

        No application data transport connections exist, but application
        network is still connected to host data network.
    .. cpp:enumerator:: Fault = 8

        Application network has ceased all activity due to an error, but
        operating storage elements have not been freed.
.. _OcaApplicationNetworkCommand:

OcaApplicationNetworkCommand
============================

.. cpp:enum:: OcaApplicationNetworkCommand : uint8_t

    Command values for OcaMediaNetwork.Control().

    .. cpp:enumerator:: None = 0

        No-op. State is not changed.
    .. cpp:enumerator:: Prepare = 1

        Open a connection to the host data network, but do not make any media
        connections. Resulting state = Ready.
    .. cpp:enumerator:: Start = 2

        Commence media data connection-making and data transfer. Resulting
        state = Running.
    .. cpp:enumerator:: Pause = 3

        Temporarily halt all media data transfer, but preserve media
        connections. Resulting state = Paused. nb To unpause, a Start command
        should be used.
    .. cpp:enumerator:: Stop = 4

        Cease data transfer and delete all media connections. Resulting state
        = Stopped.
    .. cpp:enumerator:: Reset = 5

        Cease all media transfer, delete all media transport connections, and
        disconnect from the host data network. Resulting state = NotReady.
.. _OcaNetworkMediaProtocol:

OcaNetworkMediaProtocol
=======================

.. cpp:enum:: OcaNetworkMediaProtocol : uint8_t

    Media transport protocols available.

    .. cpp:enumerator:: None = 0

        No media protocol - the network does not do media transport.
    .. cpp:enumerator:: AV3 = 1

        AVnu AV3 - RTP over AVB
    .. cpp:enumerator:: AVBTP = 2

        IEEE 1722 / 1722.1
    .. cpp:enumerator:: Dante = 3

        Pre-AV3 Dante with ATP transport
    .. cpp:enumerator:: Cobranet = 4

        Cobranet
    .. cpp:enumerator:: AES67 = 5

        AES67 network.
    .. cpp:enumerator:: SMPTEAudio = 6

        SMPTE 2022? Or 2071? (TBD)
    .. cpp:enumerator:: LiveWire = 7

        LiveWire media transport
    .. cpp:enumerator:: ExtensionPoint = 65

        Base value for addition of nonstandard (e.g. proprietary) protocol
        options
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

        OCP.3 - Character XML or JSON (tbd) version of OCA protocol, for
        serial links and other purposes.