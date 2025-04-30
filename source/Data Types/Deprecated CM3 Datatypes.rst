************************
Deprecated CM3 Datatypes
************************

.. _OcaStreamParameters:

OcaStreamParameters
===================

.. cpp:type:: OcaStreamParameters = OcaBlob

    Media stream parameters. Definition is media transport type dependent.
    Appropriate subclasses will be defined for specific X210 adaptations.

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

