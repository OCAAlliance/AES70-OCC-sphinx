***************************
Signal Generating Datatypes
***************************

.. _OcaWaveformType:

OcaWaveformType
===============

.. cpp:enum:: OcaWaveformType : uint8_t

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

.. cpp:enum:: OcaSweepType : uint8_t

    Enumeration of waveform types that can be used by OCA objects.

    .. cpp:enumerator:: Linear = 1

        Linear sweep.

    .. cpp:enumerator:: Logarithmic = 2

        Logarithmic sweep.

    .. cpp:enumerator:: None = 0

        No sweep.

