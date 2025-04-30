*************************
Deprecated Time Datatypes
*************************

.. _OcaTimeReferenceType:

OcaTimeReferenceType
====================

.. cpp:enum:: OcaTimeReferenceType : uint8_t

    Types of time references. **This datatype is deprecated as of AES70-2023.**

    .. cpp:enumerator:: Undefined = 0

        Time reference is undefined.

    .. cpp:enumerator:: Local = 1

        Time reference is internal to device.

    .. cpp:enumerator:: Private = 2

        Time reference is private to the application.

    .. cpp:enumerator:: TAI = 3

        Time reference is International Atomic Time

    .. cpp:enumerator:: ExpansionBase = 128

        Proprietary time references start here.

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

    .. cpp:enumerator:: IEEE_802_1AS = 7

        Time protocol is IEEE 802.1as.

    .. cpp:enumerator:: StreamEndpoint = 8

        Time protocol is derived from a stream endpoint.

    .. cpp:enumerator:: AES11 = 9

        Time protocol is AES11 - see [AES11].

    .. cpp:enumerator:: Genlock = 10

        Time protocol is Genlock

    .. cpp:enumerator:: ExpansionBase = 128

        Proprietary additions start here.

.. _OcaMediaClockLockState:

OcaMediaClockLockState
======================

.. cpp:enum:: OcaMediaClockLockState : uint8_t

    Lock states of media clocks.

    .. cpp:enumerator:: Undefined = 0

        Lock state is undefined.

    .. cpp:enumerator:: Locked = 1

        Media clock is locked.

    .. cpp:enumerator:: Synchronizing = 2

        Media clock is attempting to lock.

    .. cpp:enumerator:: FreeRun = 3

        Media clock is free-running.

    .. cpp:enumerator:: Stopped = 4

        Media clock is stopped.

.. _OcaMediaClockType:

OcaMediaClockType
=================

.. cpp:enum:: OcaMediaClockType : uint8_t

    Types of media clocks.

    .. cpp:enumerator:: None = 0

        No network

    .. cpp:enumerator:: Internal = 1

        Internal media clock

    .. cpp:enumerator:: Network = 2

        Network media clock

    .. cpp:enumerator:: External = 3

        External media clock input on this device

.. _OcaTimeNTP:

OcaTimeNTP
==========

.. cpp:type:: OcaTimeNTP = OcaUint64

    Time of day in NTP format

.. _OcaTimeOfDay:

OcaTimeOfDay
============

.. cpp:type:: OcaTimeOfDay = OcaUint64

    The original NTP-format time datatype used in AES70-2015. In AES70-2018

     - NTP time has been replaced by the new datatype **OcaTime**.

     - For compatibility, certain parameters with NTP time values have been
       retained, but deprecated; for clarity, the datatype of these values has
       been changed to **OcaTimeNTP. **

     - **OcaTimeNTP** is the renamed version of **OcaTimeOfDay**, and is a
       deprecated datatype.

     - This datatype, **OcaTimeOfDay**, is listed in the deprecated list for
       descriptive purposes only.



