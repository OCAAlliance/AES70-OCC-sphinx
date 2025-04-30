.. _ocasignalgenerator:

1.1.1.17  OcaSignalGenerator
============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaSignalGenerator <ocasignalgenerator>`

.. cpp:class:: OcaSignalGenerator: OcaActuator

    Multiwaveform signal generator with optional sweep capability.

    **Properties**:


    .. _ocasignalgenerator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.17"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocasignalgenerator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocasignalgenerator_frequency1:

    .. cpp:member:: OcaFrequency Frequency1

        Center frequency or sweep start frequency.

        This property has id ``4.1``.

    .. _ocasignalgenerator_frequency2:

    .. cpp:member:: OcaFrequency Frequency2

        Sweep end frequency.

        This property has id ``4.2``.

    .. _ocasignalgenerator_level:

    .. cpp:member:: OcaDBz Level

        Output level in dB relative to device-defined zero level.

        This property has id ``4.3``.

    .. _ocasignalgenerator_waveform:

    .. cpp:member:: OcaWaveformType Waveform

        The waveform type this generator generates (e.g. sine, square, noise,
        etc.).

        This property has id ``4.4``.

    .. _ocasignalgenerator_sweeptype:

    .. cpp:member:: OcaSweepType SweepType

        The sweep type of the signal generator: None for no sweep, linear or
        logarithmic if sweep is generated.

        This property has id ``4.5``.

    .. _ocasignalgenerator_sweeptime:

    .. cpp:member:: OcaTimeInterval SweepTime

        Duration of sweep in seconds.

        This property has id ``4.6``.

    .. _ocasignalgenerator_sweeprepeat:

    .. cpp:member:: OcaBoolean SweepRepeat

        Indicates whether the sweep is repeated (true) or is one-shot (false).

        This property has id ``4.7``.

    .. _ocasignalgenerator_generating:

    .. cpp:member:: OcaBoolean Generating

        Read-only property that indicates whether the generator is producing
        output (true) or not (false).

        This property has id ``4.8``.

    Properties inherited from :ref:`ocaactuator`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocasignalgenerator_getfrequency1:

    .. cpp:function:: OcaStatus GetFrequency1(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency1 property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.1``.

        - :cpp:expr:`frequency`: Output parameter.


        - :cpp:expr:`minFrequency`: Output parameter.


        - :cpp:expr:`maxFrequency`: Output parameter.


    .. _ocasignalgenerator_setfrequency1:

    .. cpp:function:: OcaStatus SetFrequency1(OcaFrequency frequency)

        Sets the value of the Frequency1 property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.2``.

        - :cpp:expr:`frequency`: Input parameter.


    .. _ocasignalgenerator_getfrequency2:

    .. cpp:function:: OcaStatus GetFrequency2(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency2 property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.3``.

        - :cpp:expr:`frequency`: Output parameter.


        - :cpp:expr:`minFrequency`: Output parameter.


        - :cpp:expr:`maxFrequency`: Output parameter.


    .. _ocasignalgenerator_setfrequency2:

    .. cpp:function:: OcaStatus SetFrequency2(OcaFrequency frequency)

        Sets the value of the Frequency2 property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.4``.

        - :cpp:expr:`frequency`: Input parameter.


    .. _ocasignalgenerator_getlevel:

    .. cpp:function:: OcaStatus GetLevel(OcaDBz &Level, OcaDBz &minLevel, OcaDBz &maxLevel)

        Gets the value of the Level property. The return value indicates whether
        the property was successfully retrieved.

        This method has id ``4.5``.

        - :cpp:expr:`Level`: Output parameter.


        - :cpp:expr:`minLevel`: Output parameter.


        - :cpp:expr:`maxLevel`: Output parameter.


    .. _ocasignalgenerator_setlevel:

    .. cpp:function:: OcaStatus SetLevel(OcaDBz Level)

        Sets the value of the Level property. The return value indicates whether
        the property was successfully set.

        This method has id ``4.6``.

        - :cpp:expr:`Level`: Input parameter.


    .. _ocasignalgenerator_getwaveform:

    .. cpp:function:: OcaStatus GetWaveform(OcaWaveformType &waveform)

        Gets the value of the Waveform property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.7``.

        - :cpp:expr:`waveform`: Output parameter.


    .. _ocasignalgenerator_setwaveform:

    .. cpp:function:: OcaStatus SetWaveform(OcaWaveformType waveform)

        Sets the value of the Waveform property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.8``.

        - :cpp:expr:`waveform`: Input parameter.


    .. _ocasignalgenerator_getsweeptype:

    .. cpp:function:: OcaStatus GetSweepType(OcaSweepType &sweepType)

        Gets the value of the SweepType property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.9``.

        - :cpp:expr:`sweepType`: Output parameter.


    .. _ocasignalgenerator_setsweeptype:

    .. cpp:function:: OcaStatus SetSweepType(OcaSweepType sweepType)

        Sets the value of the SweepType property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.10``.

        - :cpp:expr:`sweepType`: Input parameter.


    .. _ocasignalgenerator_getsweeptime:

    .. cpp:function:: OcaStatus GetSweepTime(OcaTimeInterval &sweepTime, OcaTimeInterval &minSweepTime, OcaTimeInterval &maxSweepTime)

        Gets the value of the SweepTime property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.11``.

        - :cpp:expr:`sweepTime`: Output parameter.


        - :cpp:expr:`minSweepTime`: Output parameter.


        - :cpp:expr:`maxSweepTime`: Output parameter.


    .. _ocasignalgenerator_setsweeptime:

    .. cpp:function:: OcaStatus SetSweepTime(OcaTimeInterval sweepTime)

        Sets the value of the SweepTime property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.12``.

        - :cpp:expr:`sweepTime`: Input parameter.


    .. _ocasignalgenerator_getsweeprepeat:

    .. cpp:function:: OcaStatus GetSweepRepeat(OcaBoolean &sweepRepeat)

        Gets the value of the SweepRepeat property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.13``.

        - :cpp:expr:`sweepRepeat`: Output parameter.


    .. _ocasignalgenerator_setsweeprepeat:

    .. cpp:function:: OcaStatus SetSweepRepeat(OcaBoolean sweepRepeat)

        Sets the value of the SweepRepeat property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.14``.

        - :cpp:expr:`sweepRepeat`: Input parameter.


    .. _ocasignalgenerator_getgenerating:

    .. cpp:function:: OcaStatus GetGenerating(OcaBoolean &generating)

        Gets the value of the Generating property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.15``.

        - :cpp:expr:`generating`: Output parameter.


    .. _ocasignalgenerator_start:

    .. cpp:function:: OcaStatus Start()

        Starts the signal generator. The return value indicates whether the
        signal generator was successfully started.

        This method has id ``4.16``.

    .. _ocasignalgenerator_stop:

    .. cpp:function:: OcaStatus Stop()

        Stops the signal generator. The return value indicates whether the
        signal generator was successfully stopped.

        This method has id ``4.17``.

    .. _ocasignalgenerator_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency1, OcaFrequency Frequency2, OcaDBz Level, OcaWaveformType Waveform, OcaSweepType SweepType, OcaTimeInterval SweepTime, OcaBoolean SweepRepeat)

        Sets some or all signal generation parameters. The return value
        indicates if the parameters were successfully set. The action of this
        method is atomic - if any of the value changes fails, none of the
        changes are made.

        This method has id ``4.18``.

        - :cpp:expr:`Mask`: Input parameter.


        - :cpp:expr:`Frequency1`: Input parameter.


        - :cpp:expr:`Frequency2`: Input parameter.


        - :cpp:expr:`Level`: Input parameter.


        - :cpp:expr:`Waveform`: Input parameter.


        - :cpp:expr:`SweepType`: Input parameter.


        - :cpp:expr:`SweepTime`: Input parameter.


        - :cpp:expr:`SweepRepeat`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

