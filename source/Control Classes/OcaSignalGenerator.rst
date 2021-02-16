.. _ocasignalgenerator:

1.1.1.17  OcaSignalGenerator
============================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaSignalGenerator: OcaActuator

    Multiwaveform signal generator with optional sweep capability.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaFrequency Frequency1

        This property has id ``4.0``.

        Center frequency or sweep start frequency.

    .. cpp:member:: OcaFrequency Frequency2

        This property has id ``4.0``.

        Sweep end frequency.

    .. cpp:member:: OcaDBz Level

        This property has id ``4.0``.

        Output level in dB relative to device-defined zero level.

    .. cpp:member:: OcaWaveformType Waveform

        This property has id ``4.0``.

        The waveform type this generator generates (e.g. sine, square, noise,
        etc.).

    .. cpp:member:: OcaSweepType SweepType

        This property has id ``4.0``.

        The sweep type of the signal generator: None for no sweep, linear or
        logarithmic if sweep is generated.

    .. cpp:member:: OcaTimeInterval SweepTime

        This property has id ``4.0``.

        Duration of sweep in seconds.

    .. cpp:member:: OcaBoolean SweepRepeat

        This property has id ``4.0``.

        Indicates whether the sweep is repeated (true) or is one-shot (false).

    .. cpp:member:: OcaBoolean Generating

        This property has id ``4.0``.

        Read-only property that indicates whether the generator is producing
        output (true) or not (false).

    .. cpp:function:: OcaStatus GetFrequency1(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        This method has id ``4.1``.

        Gets the value of the Frequency1 property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaFrequency frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. cpp:function:: OcaStatus SetFrequency1(OcaFrequency frequency)

        This method has id ``4.2``.

        Sets the value of the Frequency1 property. The return value indicates
        whether the property was successfully set.

        :param OcaFrequency frequency: Input parameter.

    .. cpp:function:: OcaStatus GetFrequency2(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        This method has id ``4.3``.

        Gets the value of the Frequency2 property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaFrequency frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. cpp:function:: OcaStatus SetFrequency2(OcaFrequency frequency)

        This method has id ``4.4``.

        Sets the value of the Frequency2 property. The return value indicates
        whether the property was successfully set.

        :param OcaFrequency frequency: Input parameter.

    .. cpp:function:: OcaStatus GetLevel(OcaDBz &Level, OcaDBz &minLevel, OcaDBz &maxLevel)

        This method has id ``4.5``.

        Gets the value of the Level property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaDBz Level: Output parameter.
        :param OcaDBz minLevel: Output parameter.
        :param OcaDBz maxLevel: Output parameter.

    .. cpp:function:: OcaStatus SetLevel(OcaDBz Level)

        This method has id ``4.6``.

        Sets the value of the Level property. The return value indicates
        whether the property was successfully set.

        :param OcaDBz Level: Input parameter.

    .. cpp:function:: OcaStatus GetWaveform(OcaWaveformType &waveform)

        This method has id ``4.7``.

        Gets the value of the Waveform property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaWaveformType waveform: Output parameter.

    .. cpp:function:: OcaStatus SetWaveform(OcaWaveformType waveform)

        This method has id ``4.8``.

        Sets the value of the Waveform property. The return value indicates
        whether the property was successfully set.

        :param OcaWaveformType waveform: Input parameter.

    .. cpp:function:: OcaStatus GetSweepType(OcaSweepType &sweepType)

        This method has id ``4.9``.

        Gets the value of the SweepType property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaSweepType sweepType: Output parameter.

    .. cpp:function:: OcaStatus SetSweepType(OcaSweepType sweepType)

        This method has id ``4.10``.

        Sets the value of the SweepType property. The return value indicates
        whether the property was successfully set.

        :param OcaSweepType sweepType: Input parameter.

    .. cpp:function:: OcaStatus GetSweepTime(OcaTimeInterval &sweepTime, OcaTimeInterval &minSweepTime, OcaTimeInterval &maxSweepTime)

        This method has id ``4.11``.

        Gets the value of the SweepTime property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaTimeInterval sweepTime: Output parameter.
        :param OcaTimeInterval minSweepTime: Output parameter.
        :param OcaTimeInterval maxSweepTime: Output parameter.

    .. cpp:function:: OcaStatus SetSweepTime(OcaTimeInterval sweepTime)

        This method has id ``4.12``.

        Sets the value of the SweepTime property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval sweepTime: Input parameter.

    .. cpp:function:: OcaStatus GetSweepRepeat(OcaBoolean &sweepRepeat)

        This method has id ``4.13``.

        Gets the value of the SweepRepeat property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean sweepRepeat: Output parameter.

    .. cpp:function:: OcaStatus SetSweepRepeat(OcaBoolean sweepRepeat)

        This method has id ``4.14``.

        Sets the value of the SweepRepeat property. The return value indicates
        whether the property was successfully set.

        :param OcaBoolean sweepRepeat: Input parameter.

    .. cpp:function:: OcaStatus GetGenerating(OcaBoolean &generating)

        This method has id ``4.15``.

        Gets the value of the Generating property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean generating: Output parameter.

    .. cpp:function:: OcaStatus Start()

        This method has id ``4.16``.

        Starts the signal generator. The return value indicates whether the
        signal generator was successfully started.


    .. cpp:function:: OcaStatus Stop()

        This method has id ``4.17``.

        Stops the signal generator. The return value indicates whether the
        signal generator was successfully stopped.


    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency1, OcaFrequency Frequency2, OcaDBz Level, OcaWaveformType Waveform, OcaSweepType SweepType, OcaTimeInterval SweepTime, OcaBoolean SweepRepeat)

        This method has id ``4.18``.

        Sets some or all signal generation parameters. The return value
        indicates if the parameters were successfully set. The action of this
        method is atomic - if any of the value changes fails, none of the
        changes are made.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency1: Input parameter.
        :param OcaFrequency Frequency2: Input parameter.
        :param OcaDBz Level: Input parameter.
        :param OcaWaveformType Waveform: Input parameter.
        :param OcaSweepType SweepType: Input parameter.
        :param OcaTimeInterval SweepTime: Input parameter.
        :param OcaBoolean SweepRepeat: Input parameter.

