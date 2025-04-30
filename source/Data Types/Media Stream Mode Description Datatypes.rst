***************************************
Media Stream Mode Description Datatypes
***************************************

.. _OcaMediaStreamMode:

OcaMediaStreamMode
==================

.. cpp:struct:: OcaMediaStreamMode

    Current media stream mode descriptor.

    .. cpp:member:: OcaMediaFrameFormat FrameFormat

        Media frame format

    .. cpp:member:: OcaMimeType EncodingType

        Media encoding type

    .. cpp:member:: OcaFrequency SamplingRate

        Media sampling rate

    .. cpp:member:: OcaUint16 ChannelCount

        Number of signal channels in the stream

    .. cpp:member:: OcaTimeInterval PacketTime

        Duration of the media signal fragment carried in a single network
        packet.

.. _OcaMediaStreamModeCapability:

OcaMediaStreamModeCapability
============================

.. cpp:struct:: OcaMediaStreamModeCapability

    Media stream mode capability descriptor.

    .. cpp:member:: OcaID16 ID

        ID of this capability

    .. cpp:member:: OcaString Name

        Arbitrary user-supplied name of this capability

    .. cpp:member:: OcaMediaStreamModeCapabilityDirection Direction

        Supported input/output direction - input, output, or both.

    .. cpp:member:: OcaList<OcaMediaFrameFormat> FrameFormatList

        Supported frame formats

    .. cpp:member:: OcaList<OcaMimeType> EncodingTypeList

        Supported encoding types

    .. cpp:member:: OcaList<OcaFrequency> SamplingRateList

        Supported sampling rates

    .. cpp:member:: OcaList<OcaUint16> ChannelCountList

        Supported channel count list. If both a list and a range are specified,
        the capability includes all channel counts within the union of the two
        constraints.

    .. cpp:member:: OcaInterval<OcaUint16> ChannelCountRange

        Supported channel count range. If both a list and a range are specified,
        the capability includes all channel counts within the union of the two
        constraints.

    .. cpp:member:: OcaList<OcaTimeInterval> PacketTimeList

        Supported packet-time value list. If both a list and a range are
        specified, the capability includes all packet times within the union of
        the two constraints.

    .. cpp:member:: OcaInterval<OcaTimeInterval> PacketTimeRange

        Range of supported packet-time values. If both a list and a range are
        specified, the capability includes all packet times within the union of
        the two constraints.

.. _OcaMediaFrameFormat:

OcaMediaFrameFormat
===================

.. cpp:enum:: OcaMediaFrameFormat : uint8_t

    Media stream frame formats.

    .. cpp:enumerator:: Undefined = 0

        Undefined frame format

    .. cpp:enumerator:: RTP = 1

        Real-Time Transport Protocol (RTP) frame format. RTP is specified in
        [RFC 3550].

    .. cpp:enumerator:: AAF = 2

        AAF ("AVTP Audio Format") frame, as defined in IEEE 1722.1. Note: This
        is not the same as Advanced Authoring Format.

    .. cpp:enumerator:: CRF_MILAN = 3

        CRF_Milan format. Frame format of clock reference streams defined by the
        **Milan** profile of IEEE AVB.

    .. cpp:enumerator:: IEC_61883_6 = 4

        [IEC 61883-6] format. Audio transport frame format used by IEEE 1394
        (FireWire)

    .. cpp:enumerator:: USB_AUDIO_2_0 = 5

        Frame format for USB 2.0 media transport.

    .. cpp:enumerator:: ExtensionPoint = 65

        Nonstandard values start at this number.

.. _OcaMediaStreamModeCapabilityDirection:

OcaMediaStreamModeCapabilityDirection
=====================================

.. cpp:type:: OcaMediaStreamModeCapabilityDirection = OcaBitSet16

    Bitset describing the I/O direction(s) an Endpoint supports.

