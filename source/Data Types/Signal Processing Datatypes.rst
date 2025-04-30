***************************
Signal Processing Datatypes
***************************

.. _OcaMuteState:

OcaMuteState
============

.. cpp:enum:: OcaMuteState : uint8_t

    Mute states

    .. cpp:enumerator:: Muted = 1


    .. cpp:enumerator:: Unmuted = 2


.. _OcaPolarityState:

OcaPolarityState
================

.. cpp:enum:: OcaPolarityState : uint8_t

    Polarity states

    .. cpp:enumerator:: NonInverted = 1


    .. cpp:enumerator:: Inverted = 2


.. _OcaTransferFunction:

OcaTransferFunction
===================

.. cpp:struct:: OcaTransferFunction

    Complex (i.e. magnitude + phase) transfer function.

    .. cpp:member:: OcaList<OcaFrequency> Frequency

        Frequencies

    .. cpp:member:: OcaList<OcaFloat32> Amplitude

        Amplitude (not in dB)

    .. cpp:member:: OcaList<OcaFloat32> Phase

        Phase in radians.

.. _OcaClassicalFilterShape:

OcaClassicalFilterShape
=======================

.. cpp:enum:: OcaClassicalFilterShape : uint8_t

    Enumeration of classical filter shapes

    .. cpp:enumerator:: Butterworth = 1

        Butterworth

    .. cpp:enumerator:: Bessel = 2

        Bessel

    .. cpp:enumerator:: Chebyshev = 3

        Chebyshev. In **OcaFilterClassical**, ripple factor is specified by the
        **Parameter** property.

    .. cpp:enumerator:: LinkwitzRiley = 4

        Linkwitz-Riley

.. _OcaFilterPassband:

OcaFilterPassband
=================

.. cpp:enum:: OcaFilterPassband : uint8_t

    Enumeration of passband types that can be used by OCA objects.

    .. cpp:enumerator:: HiPass = 1


    .. cpp:enumerator:: LowPass = 2


    .. cpp:enumerator:: BandPass = 3


    .. cpp:enumerator:: BandReject = 4


    .. cpp:enumerator:: AllPass = 5


.. _OcaParametricEQShape:

OcaParametricEQShape
====================

.. cpp:enum:: OcaParametricEQShape : uint8_t

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

        Bass control with fixed hinge point.

    .. cpp:enumerator:: ToneControlLowSliding = 10

        Bass control with sliding hinge point (e.g. Baxandall)

    .. cpp:enumerator:: ToneControlHighFixed = 11

        Treble control with fixed hinge point.

    .. cpp:enumerator:: ToneControlHighSliding = 12

        Treble control with sliding hinge point (e.g. Baxandall)

.. _OcaDynamicsFunction:

OcaDynamicsFunction
===================

.. cpp:enum:: OcaDynamicsFunction : uint8_t

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

        Gate function (downward expand with fixed 'infinite' downward expansion
        ratio).

.. _OcaSamplingRateConverterType:

OcaSamplingRateConverterType
============================

.. cpp:enum:: OcaSamplingRateConverterType : uint8_t

    Types of sampling rate converters

    .. cpp:enumerator:: None = 0

        No sampling rate converter

    .. cpp:enumerator:: Synchronous = 1

        Synchronous sampling rate converter

    .. cpp:enumerator:: Asynchronous = 2

        Asynchronous sampling rate converter

