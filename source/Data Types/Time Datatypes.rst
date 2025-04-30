**************
Time Datatypes
**************

.. _OcaMediaClockAvailability:

OcaMediaClockAvailability
=========================

.. cpp:enum:: OcaMediaClockAvailability : uint8_t

    Availability states of a Media Clock

    .. cpp:enumerator:: Unavailable = 0

        Media Clock is unavailable.

    .. cpp:enumerator:: Available = 1

        Media Clock is available.

.. _OcaMediaClockRate:

OcaMediaClockRate
=================

.. cpp:struct:: OcaMediaClockRate

    Media Clock nominal rate and associated parameters.

    .. cpp:member:: OcaFrequency NominalRate

        Nominal clock rate, in hertz.

    .. cpp:member:: OcaFrequency PullRange

        Pull range in hertz. Not all clock types will specify this. Use IEEE NaN
        for an unspecified value (OcaFrequency is IEEE floating-point).

    .. cpp:member:: OcaFloat32 Accuracy

        Accuracy in ppm. Not all clock types will specify this. Use IEEE NaN for
        an unspecified value.

    .. cpp:member:: OcaFloat32 JitterMax

        Maximum jitter in ppm. Not all clock types will specify this. Use IEEE
        NaN foran unspecified value.

.. _OcaTimeMode:

OcaTimeMode
===========

.. cpp:enum:: OcaTimeMode : uint8_t

    Time mode of **OcaTask** agent.

    .. cpp:enumerator:: Absolute = 1

        OcaRamper or OcaTask time mode is absolute.

    .. cpp:enumerator:: Relative = 2

        OcaRamper or OcaTask time mode is relative.

.. _OcaTime:

OcaTime
=======

.. cpp:struct:: OcaTime

    Absolute or relative time. Time values in PTP presentation format with added
    sign. - 48 bit integer seconds - 32 bit integer nanoseconds - boolean sign
    (positive=TRUE) field. Absolute times are always positive. Relative times
    may be positive or negative.

    .. cpp:member:: OcaBoolean Negative

        TRUE if and only if time value is negative. Absolute times are always
        positive.

    .. cpp:member:: OcaUint64 Seconds

        64-bit integer whose value shall not exceed that of an unsigned 48 bit
        integer.

    .. cpp:member:: OcaUint32 Nanoseconds

        32 bits of nanoseconds

.. _OcaTimeInterval:

OcaTimeInterval
===============

.. cpp:type:: OcaTimeInterval = OcaFloat32

    Time interval in seconds.

