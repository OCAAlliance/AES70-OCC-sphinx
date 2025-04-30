**************
Time Datatypes
**************

.. _OcaMediaClockAvailability:

OcaMediaClockAvailability
=========================

.. cpp:enum:: OcaMediaClockAvailability : uint8_t

    Lock states of media clocks.

    .. cpp:enumerator:: Unavailable = 0

        Media clock is unavailable.

    .. cpp:enumerator:: Available = 1

        Media clock is available.

.. _OcaMediaClockRate:

OcaMediaClockRate
=================

.. cpp:struct:: OcaMediaClockRate

    Media clock nominal rate and associated parameters.

    .. cpp:member:: OcaFrequency NominalRate

        Nominal clock rate, in hertz.

    .. cpp:member:: OcaFrequency PullRange

        Pull range in hertz. Not all clock types will specify this. Use IEEE NaN
        for unspecified value (OcaFrequency is IEEE floating-point).

    .. cpp:member:: OcaFloat32 Accuracy

        Accuracy in ppm. Not all clock types will specify this. Use IEEE NaN for
        unspecified value.

    .. cpp:member:: OcaFloat32 JitterMax

        Maximum jitter in ppm. Not all clock types will specify this. Use IEEE
        NaN for unspecified value.

.. _OcaTimeReferenceType:

OcaTimeReferenceType
====================

.. cpp:enum:: OcaTimeReferenceType : uint8_t

    Types of time references.

    .. cpp:enumerator:: Undefined = 0

        Time reference is undefined.

    .. cpp:enumerator:: Local = 1

        Time reference is internal to device.

    .. cpp:enumerator:: Private = 2

        Time reference is private to the application.

    .. cpp:enumerator:: GPS = 3

        Time reference is the U.S. Global Positioning System (GPS).

    .. cpp:enumerator:: Galileo = 4

        Time reference is the European Galileo global positioning system.

    .. cpp:enumerator:: GLONASS = 5

        Time reference is the Russian GLONASS global positioning system.

.. _OcaTimeProtocol:

OcaTimeProtocol
===============

.. cpp:enum:: OcaTimeProtocol : uint8_t

    Types of time sources. See RFC7273 particularly sections 4.4-4.8 .

    .. cpp:enumerator:: Undefined = 0

        Time protocol is undefined.

    .. cpp:enumerator:: None = 1

        Time reference is inside device, so no network time protocol is used.

    .. cpp:enumerator:: Private = 2

        Time protocol is not a public standard.

    .. cpp:enumerator:: NTP = 3

        Time protocol is Network Time Protocol.

    .. cpp:enumerator:: SNTP = 4

        Time protocol is Simple Network Time Protocol.

    .. cpp:enumerator:: IEEE1588_2002 = 5

        Time protocol is PTP (IEEE 1588), older version.

    .. cpp:enumerator:: IEEE1588_2008 = 6

        Time protocol is PTP (IEEE 1588), newer version.

    .. cpp:enumerator:: IEEE_AVB = 7

        Time protocol is IEEE 802.1as.

    .. cpp:enumerator:: AES11 = 8

        Time protocol is AES11.

    .. cpp:enumerator:: Genlock = 9

        Time protocol is Genlock

.. _OcaTimeSourceAvailability:

OcaTimeSourceAvailability
=========================

.. cpp:enum:: OcaTimeSourceAvailability : uint8_t

    States of time sources

    .. cpp:enumerator:: Unavailable = 0

        Time source is unavailable.

    .. cpp:enumerator:: Available = 1

        Time source is available.

.. _OcaTimeMode:

OcaTimeMode
===========

.. cpp:enum:: OcaTimeMode : uint8_t

    Time mode of **OcaTask** agent.

    .. cpp:enumerator:: Absolute = 1

        OcaRamper or OcaTask time mode is absolute.

    .. cpp:enumerator:: Relative = 2

        OcaRamper or OcaTask time mode is relative.

.. _OcaTimeSourceSyncStatus:

OcaTimeSourceSyncStatus
=======================

.. cpp:enum:: OcaTimeSourceSyncStatus : uint8_t

    Synchronization statuses.

    .. cpp:enumerator:: Undefined = 0

        Lock state is undefined.

    .. cpp:enumerator:: Unsynchronized = 1

        Time source is not synchronized to reference.

    .. cpp:enumerator:: Synchronizing = 2

        Time source is attempting to synchronize to reference.

    .. cpp:enumerator:: Synchronized = 3

        Time source is synchronized with reference.

.. _OcaPTPSeconds:

OcaPTPSeconds
=============

.. cpp:type:: OcaPTPSeconds = OcaUint64

    PTP seconds. Defined as a 64 bit unsigned integer for ease of programming;
    however, the value shall not exceed that of a 48-bit unsigned integer.

.. _OcaTimePTP:

OcaTimePTP
==========

.. cpp:struct:: OcaTimePTP

    An absolute or relative PTP time. Format is standard PTP format: - 48 bit
    integer seconds - 32 bit integer nanoseconds PLUS a boolean sign
    (positive=TRUE) field. Absolute times are always positive. Relative times
    may be positive or negative.

    .. cpp:member:: OcaBoolean Negative

        TRUE if and only if time value is negative. Absolute times are always
        positive.

    .. cpp:member:: OcaPTPSeconds Seconds

        48 bits of seconds

    .. cpp:member:: OcaUint32 Nanoseconds

        32 bits of nano seconds

.. _OcaTimeInterval:

OcaTimeInterval
===============

.. cpp:type:: OcaTimeInterval = OcaFloat32

    Strong datatype for time interval in seconds.

