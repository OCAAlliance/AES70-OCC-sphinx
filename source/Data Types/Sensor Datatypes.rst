****************
Sensor Datatypes
****************

.. _OcaImpedance:

OcaImpedance
============

.. cpp:struct:: OcaImpedance

    Complex impedance. Expressed as a magnitude and phase.

    .. cpp:member:: OcaFloat32 Magnitude

        Impedance magnitude in ohms.

    .. cpp:member:: OcaFloat32 Phase

        Impedance phase in radians.

.. _OcaLevelDetectionLaw:

OcaLevelDetectionLaw
====================

.. cpp:enum:: OcaLevelDetectionLaw : uint8_t

    Enumeration of the types of level detector characteristics. Used in dynamics
    classes and for sensors.

    .. cpp:enumerator:: None = 0

        No detection (i.e. never trigger)

    .. cpp:enumerator:: RMS = 1

        Detect RMS value.

    .. cpp:enumerator:: Peak = 2

        Detect peak value.

.. _OcaSensorReadingState:

OcaSensorReadingState
=====================

.. cpp:enum:: OcaSensorReadingState : uint8_t

    Enum that describes whether an **OcaSensor**'s current reading value can be
    trusted, and if not, why not.

    .. cpp:enumerator:: Unknown = 0

        Cannot determine validity of reading, or this feature is not
        implemented.

    .. cpp:enumerator:: Valid = 1

        Sensor reading is valid.

    .. cpp:enumerator:: Underrange = 2

        Sensor is underrange, reading is not valid.

    .. cpp:enumerator:: Overrange = 3

        Sensor is overrange, reading is not valid.

    .. cpp:enumerator:: Error = 4

        Sensor is in an error state, reading is not valid.

.. _OcaLevelMeterLaw:

OcaLevelMeterLaw
================

.. cpp:enum:: OcaLevelMeterLaw : uint8_t

    Enumeration of level meter laws.

    .. cpp:enumerator:: VU = 1

        Generic VU-style meter, characteristics defined by device.

    .. cpp:enumerator:: StandardVU = 2

        Classic VU meter per ANSI C16.5-1942, British Standard BS 6840, and IEC
        60268-17.

    .. cpp:enumerator:: PPM1 = 3

        IEC 60268-10 Peak Programme Meter, type I (Germany).

    .. cpp:enumerator:: PPM2 = 4

        IEC 60268-10 Peak Programme Meter, type II (BBC).

    .. cpp:enumerator:: LKFS = 5

        Loudness meter as defined by ITU BS1770.

    .. cpp:enumerator:: RMS = 6

        Simple RMS meter

    .. cpp:enumerator:: Peak = 7

        Simple peak meter

    .. cpp:enumerator:: ProprietaryValueBase = 128

        Proprietery classes shall add values of this value or greater. Values 0
        to 127 are reserved.

