***************************
Deprecated Worker Datatypes
***************************

.. _OcaDelayUnit:

OcaDelayUnit
============

.. cpp:enum:: OcaDelayUnit : uint8_t

    Enumeration of types of delay units that are available in AES70. This
    enumeration is **deprecated** in AES70-2022.

    .. cpp:enumerator:: Time = 1

        PTP time value

    .. cpp:enumerator:: Distance = 2


    .. cpp:enumerator:: Samples = 3


    .. cpp:enumerator:: Microseconds = 4


    .. cpp:enumerator:: Milliseconds = 5


    .. cpp:enumerator:: Centimeters = 6


    .. cpp:enumerator:: Inches = 7


    .. cpp:enumerator:: Feet = 8


.. _OcaDelayValue:

OcaDelayValue
=============

.. cpp:struct:: OcaDelayValue

    Multifield descriptor that defines a delay value element. This datatype is
    **deprecated** in AES70-2022.

    .. cpp:member:: OcaFloat32 DelayValue

        The delay value.

    .. cpp:member:: OcaDelayUnit DelayUnit

        The unit of the delay value.

.. _OcaPeriod:

OcaPeriod
=========

.. cpp:type:: OcaPeriod = OcaUint32

    General-purpose period of time in milliseconds. Deprecated in OCA 1.5. New
    designs should use **OcaTimeInterval** instead.

.. _OcaPilotToneDetectorSpec:

OcaPilotToneDetectorSpec
========================

.. cpp:struct:: OcaPilotToneDetectorSpec

    Multifield descriptor for a pilot tone detector element. Deprecated in OCA
    1.5.

    .. cpp:member:: OcaDBr Threshold

        Tone level threshold in dB.

    .. cpp:member:: OcaFrequency Frequency

        Frequency of the measured tone (in Hz).

    .. cpp:member:: OcaPeriod PollInterval

        Poll interval in milliseconds.

