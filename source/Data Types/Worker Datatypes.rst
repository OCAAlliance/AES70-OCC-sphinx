****************
Worker Datatypes
****************

.. _OcaDB:

OcaDB
=====

.. cpp:type:: OcaDB = OcaFloat32

    A ratio expressed in dB. Typically used for gain settings.
.. _OcaDBr:

OcaDBr
======

.. cpp:struct:: OcaDBr
    
    An absolute level expressed in dB above the given absolute reference
    level.

    .. cpp:member:: OcaDB Value

        Absolute level in decibels relative to value of **Ref** property.

    .. cpp:member:: OcaDBz Ref

        Reference level in dBz. See the definition of OcaDBz for an
        explanation of the dBz unit.


OCP.1 Encoding
--------------

=============== ========== ===========
Field           Basic type Byte length
=============== ========== ===========
Value.Value     OcaFloat32 4          
Ref.Value.Value OcaFloat32 4          
=============== ========== ===========


.. _OcaDBV:

OcaDBV
======

.. cpp:type:: OcaDBV = OcaDB

    An absolute analogue level expressed in dB re 1 volt. This datatype
    may only be used for parameters that reflect analogue signal values,
    e.g. pre-ADC input signals and post-DAC output signals.
.. _OcaDBu:

OcaDBu
======

.. cpp:type:: OcaDBu = OcaDB

    An absolute analogue level expressed in dB re 0.774 volts. This
    datatype may only be used for parameters that reflect analogue signal
    values, e.g. pre-ADC input signals and post-DAC output signals.
.. _OcaDBFS:

OcaDBFS
=======

.. cpp:type:: OcaDBFS = OcaDB

    An absolute level value for digital signals, expressed in dB relative
    to the device maximum internal digital sample value. For example, a
    digital signal whose peak sample value is 7dB below the maximum
    digital sample value shall be said to have a peak level of -7 dBFS.
.. _OcaDBz:

OcaDBz
======

.. cpp:type:: OcaDBz = OcaDB

    An absolute level expressed in dB relative to the nominal device
    operating level. The nominal device operating level is a
    device-specific signal level chosen as a normal or typical signal
    amplitude for the device.
.. _OcaVoltage:

OcaVoltage
==========

.. cpp:type:: OcaVoltage = OcaFloat32

    Voltage in volts.
.. _OcaCurrent:

OcaCurrent
==========

.. cpp:type:: OcaCurrent = OcaFloat32

    Current in amperes
.. _OcaImpedance:

OcaImpedance
============

.. cpp:struct:: OcaImpedance
    
    Complex impedance. Expressed as a magnitude and phase.

    .. cpp:member:: OcaFloat32 Magnitude

        Impedance magnitude in ohms.

    .. cpp:member:: OcaFloat32 Phase

        Impedance phase in radians.


OCP.1 Encoding
--------------

========= ========== ===========
Field     Basic type Byte length
========= ========== ===========
Magnitude OcaFloat32 4          
Phase     OcaFloat32 4          
========= ========== ===========


.. _OcaMuteState:

OcaMuteState
============

.. cpp:enum-struct:: OcaMuteState

    Mute states

    .. cpp:enumerator:: Muted = 1

    .. cpp:enumerator:: Unmuted = 2

.. _OcaPolarityState:

OcaPolarityState
================

.. cpp:enum-struct:: OcaPolarityState

    Polarity states

    .. cpp:enumerator:: NonInverted = 1

    .. cpp:enumerator:: Inverted = 2

.. _OcaDelayUnit:

OcaDelayUnit
============

.. cpp:enum-struct:: OcaDelayUnit

    Enumeration of types of delay units that are available in OCA.

    .. cpp:enumerator:: Time = 1

        Time
    .. cpp:enumerator:: Distance = 2

        Distance
    .. cpp:enumerator:: Samples = 3

        Samples
    .. cpp:enumerator:: Microseconds = 4

        Samples
    .. cpp:enumerator:: Milliseconds = 5

        Samples
    .. cpp:enumerator:: Centimeters = 6

        Samples
    .. cpp:enumerator:: Inches = 7

        Samples
    .. cpp:enumerator:: Feet = 8

        Samples
.. _OcaDelayValue:

OcaDelayValue
=============

.. cpp:struct:: OcaDelayValue
    
    Multifield descriptor that defines a delay value element.

    .. cpp:member:: OcaFloat32 DelayValue

        The delay value.

    .. cpp:member:: OcaDelayUnit DelayUnit

        The unit of the delay value.


OCP.1 Encoding
--------------

========== =========== ===========
Field      Basic type  Byte length
========== =========== ===========
DelayValue OcaFloat32  4          
DelayUnit  OcaEnumItem 1          
========== =========== ===========


.. _OcaFrequency:

OcaFrequency
============

.. cpp:type:: OcaFrequency = OcaFloat32

    Strong datatype for frequency in Hertz.
.. _OcaFrequencyResponse:

OcaFrequencyResponse
====================

.. cpp:type:: OcaFrequencyResponse = OcaMap<OcaFrequency, OcaDB>

    Strong datatype for frequency response.
.. _OcaTransferFunction:

OcaTransferFunction
===================

.. cpp:struct:: OcaTransferFunction
    
    A complex (i.e. magnitude + phase) transfer function.

    .. cpp:member:: OcaList<OcaFrequency> Frequency

        Frequencies

    .. cpp:member:: OcaList<OcaFloat32> Amplitude

        Amplitude (not in dB)

    .. cpp:member:: OcaList<OcaFloat32> Phase

        Phase in radians.


OCP.1 Encoding
--------------

========= =================== ===============
Field     Basic type          Byte length    
========= =================== ===============
Frequency OcaList<OcaFloat32> (2 + 4 * Count)
Amplitude OcaList<OcaFloat32> (2 + 4 * Count)
Phase     OcaList<OcaFloat32> (2 + 4 * Count)
========= =================== ===============


.. _OcaPeriod:

OcaPeriod
=========

.. cpp:type:: OcaPeriod = OcaUint32

    General-purpose period of time in milliseconds. As this type is mostly
    used for management purposes an integer base type is used and it is
    expressed in milliseconds.
.. _OcaClassicalFilterShape:

OcaClassicalFilterShape
=======================

.. cpp:enum-struct:: OcaClassicalFilterShape

    Enumeration of classicalr filter types that can be used by OCA
    objects.

    .. cpp:enumerator:: Butterworth = 1

        Butterworth
    .. cpp:enumerator:: Bessel = 2

        Bessel
    .. cpp:enumerator:: Chebyshev = 3

        Linkwitz-Riley
    .. cpp:enumerator:: LinkwitzRiley = 4

        Linkwitz-Riley
.. _OcaFilterPassband:

OcaFilterPassband
=================

.. cpp:enum-struct:: OcaFilterPassband

    Enumeration of passband types that can be used by OCA objects.

    .. cpp:enumerator:: HiPass = 1

        High pass
    .. cpp:enumerator:: LowPass = 2

        Low pass
    .. cpp:enumerator:: BandPass = 3

        All pass
    .. cpp:enumerator:: BandReject = 4

        All pass
    .. cpp:enumerator:: AllPass = 5

        All pass
.. _OcaParametricEQShape:

OcaParametricEQShape
====================

.. cpp:enum-struct:: OcaParametricEQShape

    Enumeration of curve shapes used by OcaFilterParametric.

    .. cpp:enumerator:: None = 0

        No filter (i.e. flat frequency response)
    .. cpp:enumerator:: PEQ = 1

        PEQ
    .. cpp:enumerator:: LowShelv = 2

        Low Shelv
    .. cpp:enumerator:: HighShelv = 3

        High Shelv
    .. cpp:enumerator:: LowPass = 4

        Low Pass
    .. cpp:enumerator:: HighPass = 5

        High Pass
    .. cpp:enumerator:: BandPass = 6

        Band Pass
    .. cpp:enumerator:: AllPass = 7

        All Pass
    .. cpp:enumerator:: Notch = 8

        Notch
    .. cpp:enumerator:: ToneControlLowFixed = 9

        Notch
    .. cpp:enumerator:: ToneControlLowSliding = 10

        Notch
    .. cpp:enumerator:: ToneControlHighFixed = 11

        Notch
    .. cpp:enumerator:: ToneControlHighSliding = 12

        Notch
.. _OcaDynamicsFunction:

OcaDynamicsFunction
===================

.. cpp:enum-struct:: OcaDynamicsFunction

    Enumeration of the types of dynamics functions available from class
    OcaDynamics.

    .. cpp:enumerator:: None = 0

        No dynamic function.
    .. cpp:enumerator:: Compress = 1

        Upward compress function (reduce gain when input is above the given
        threshold).
    .. cpp:enumerator:: Limit = 2

        Limit function (compress with a fixed ratio of 10:1 or greater).
    .. cpp:enumerator:: Expand = 3

        Downward expand function (decrease gain when input is below the given
        threshhold).
    .. cpp:enumerator:: Gate = 4

        Gate function (expand with fixed 'infinite' downward expansion ratio).
.. _OcaPilotToneDetectorSpec:

OcaPilotToneDetectorSpec
========================

.. cpp:struct:: OcaPilotToneDetectorSpec
    
    Multifield descriptor for a pilot tone detector element.

    .. cpp:member:: OcaDBr Threshold

        Tone level threshold in dB.

    .. cpp:member:: OcaFrequency Frequency

        Frequency of the measured tone (in Hz).

    .. cpp:member:: OcaPeriod PollInterval

        Poll interval in milliseconds.


OCP.1 Encoding
--------------

========================= ========== ===========
Field                     Basic type Byte length
========================= ========== ===========
Threshold.Value.Value     OcaFloat32 4          
Threshold.Ref.Value.Value OcaFloat32 4          
Frequency.Hz              OcaFloat32 4          
PollInterval.Period       OcaUint32  4          
========================= ========== ===========


.. _OcaWaveformType:

OcaWaveformType
===============

.. cpp:enum-struct:: OcaWaveformType

    Enumeration of waveform types that can be used by OCA objects.

    .. cpp:enumerator:: None = 0

        No signal.
    .. cpp:enumerator:: DC = 1

        Direct current.
    .. cpp:enumerator:: Sine = 2

        Sine wave.
    .. cpp:enumerator:: Square = 3

        Square wave.
    .. cpp:enumerator:: Impulse = 4

        Impulse waveform.
    .. cpp:enumerator:: NoisePink = 5

        Pink noise waveform.
    .. cpp:enumerator:: NoiseWhite = 6

        White noise waveform.
    .. cpp:enumerator:: PolarityTest = 7

        Polarity test waveform (asymmetrical).
.. _OcaSweepType:

OcaSweepType
============

.. cpp:enum-struct:: OcaSweepType

    Enumeration of waveform types that can be used by OCA objects.

    .. cpp:enumerator:: Linear = 1

        Linear sweep.
    .. cpp:enumerator:: Logarithmic = 2

        Logarithmic sweep.
    .. cpp:enumerator:: None = 0

        No sweep.
.. _OcaUnitOfMeasure:

OcaUnitOfMeasure
================

.. cpp:enum-struct:: OcaUnitOfMeasure

    Enumeration of units of measure that can be used in OCA classes. Only
    SI (base or derived) units are specified, so that internal
    calculations will not need to convert. If conversion is needed it
    should only be done in user interfaces. The datatype of a reading
    expressed in one of these units of measure is FLOAT.

    .. cpp:enumerator:: Ampere = 4

        Electric current in Amperes.
    .. cpp:enumerator:: DegreeCelsius = 2

        Temperature in degree Celsius.
    .. cpp:enumerator:: Hertz = 1

        Frequency in Hertz.
    .. cpp:enumerator:: None = 0

        No reading.
    .. cpp:enumerator:: Ohm = 5

        Resistance, magnitude of reactance, or magnitude of impedance in Ohms.
    .. cpp:enumerator:: Volt = 3

        Voltage in Volts.
.. _OcaPresentationUnit:

OcaPresentationUnit
===================

.. cpp:enum-struct:: OcaPresentationUnit

    Enumeration of presentation units that can be used in OCA classes.
    Property values of OCA objects are always in SI units (unless
    explicitly documented otherwise), but the presentation unit can also
    be stored to indicate in which unit the value was presented in a user
    interface. This way another controller can also present it in that
    unit (i.e. doing a conversion on the controller before presenting it)
    to keep the user presentation uniform. Note that the presentation unit
    may be equal to the unit of the property (in which case of course no
    conversion is needed).

    .. cpp:enumerator:: dBu = 0

        dB(0.775 VRMS) - voltage relative to 0.775 volts.
    .. cpp:enumerator:: dBV = 1

        dB(1 VRMS) - voltage relative to 1 volt.
    .. cpp:enumerator:: V = 2

        Voltage in plain volts.
.. _OcaTemperature:

OcaTemperature
==============

.. cpp:type:: OcaTemperature = OcaFloat32

    Strong datatype for temperature in degrees Celsius.
.. _OcaLevelDetectionLaw:

OcaLevelDetectionLaw
====================

.. cpp:enum-struct:: OcaLevelDetectionLaw

    Enumeration of the types of level detector characteristics. Used in
    dynamics classes and for sensors.

    .. cpp:enumerator:: None = 0

        No detection (i.e. never trigger)
    .. cpp:enumerator:: RMS = 1

        Detect RMS value.
    .. cpp:enumerator:: Peak = 2

        Detect peak value.
.. _OcaSensorReadingState:

OcaSensorReadingState
=====================

.. cpp:enum-struct:: OcaSensorReadingState

    Enum that describes whether an **OcaSensor** 's current reading value
    can be trusted, and if not, why not.

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

.. cpp:enum-struct:: OcaLevelMeterLaw

    Enumeration of level meter laws.

    .. cpp:enumerator:: VU = 1

        Generic VU-style meter, characteristics defined by device.
    .. cpp:enumerator:: StandardVU = 2

        Classic VU meter per ANSI C16.5-1942, British Standard BS 6840, and
        IEC 60268-17.
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

        Proprietery classes shall add values of this value or greater. Values
        0 to 127 are reserved.