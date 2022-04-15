.. _ocasignalgenerator:

1.1.1.17  OcaSignalGenerator
============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaSignalGenerator <ocasignalgenerator>` 

.. cpp:class:: OcaSignalGenerator: OcaActuator

    Multiwaveform signal generator with optional sweep capability.

    **Properties**:

    .. _ocasignalgenerator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.17"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocasignalgenerator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

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

        The waveform type this generator generates (e.g. sine, square, noise, etc.).

        This property has id ``4.4``.

    .. _ocasignalgenerator_sweeptype:

    .. cpp:member:: OcaSweepType SweepType

        The sweep type of the signal generator: None for no sweep, linear or logarithmic if sweep is generated.

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

        Read-only property that indicates whether the generator is producing output (true) or not (false).

        This property has id ``4.8``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocasignalgenerator_getfrequency1:

    .. cpp:function:: OcaStatus GetFrequency1(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency1 property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.1``.

        :param OcaFrequency frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. _ocasignalgenerator_setfrequency1:

    .. cpp:function:: OcaStatus SetFrequency1(OcaFrequency frequency)

        Sets the value of the Frequency1 property. The return value indicates whether the property was successfully set.

        This method has id ``4.2``.

        :param OcaFrequency frequency: Input parameter.

    .. _ocasignalgenerator_getfrequency2:

    .. cpp:function:: OcaStatus GetFrequency2(OcaFrequency &frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency2 property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.3``.

        :param OcaFrequency frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. _ocasignalgenerator_setfrequency2:

    .. cpp:function:: OcaStatus SetFrequency2(OcaFrequency frequency)

        Sets the value of the Frequency2 property. The return value indicates whether the property was successfully set.

        This method has id ``4.4``.

        :param OcaFrequency frequency: Input parameter.

    .. _ocasignalgenerator_getlevel:

    .. cpp:function:: OcaStatus GetLevel(OcaDBz &Level, OcaDBz &minLevel, OcaDBz &maxLevel)

        Gets the value of the Level property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.5``.

        :param OcaDBz Level: Output parameter.
        :param OcaDBz minLevel: Output parameter.
        :param OcaDBz maxLevel: Output parameter.

    .. _ocasignalgenerator_setlevel:

    .. cpp:function:: OcaStatus SetLevel(OcaDBz Level)

        Sets the value of the Level property. The return value indicates whether the property was successfully set.

        This method has id ``4.6``.

        :param OcaDBz Level: Input parameter.

    .. _ocasignalgenerator_getwaveform:

    .. cpp:function:: OcaStatus GetWaveform(OcaWaveformType &waveform)

        Gets the value of the Waveform property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.7``.

        :param OcaWaveformType waveform: Output parameter.

    .. _ocasignalgenerator_setwaveform:

    .. cpp:function:: OcaStatus SetWaveform(OcaWaveformType waveform)

        Sets the value of the Waveform property. The return value indicates whether the property was successfully set.

        This method has id ``4.8``.

        :param OcaWaveformType waveform: Input parameter.

    .. _ocasignalgenerator_getsweeptype:

    .. cpp:function:: OcaStatus GetSweepType(OcaSweepType &sweepType)

        Gets the value of the SweepType property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.9``.

        :param OcaSweepType sweepType: Output parameter.

    .. _ocasignalgenerator_setsweeptype:

    .. cpp:function:: OcaStatus SetSweepType(OcaSweepType sweepType)

        Sets the value of the SweepType property. The return value indicates whether the property was successfully set.

        This method has id ``4.10``.

        :param OcaSweepType sweepType: Input parameter.

    .. _ocasignalgenerator_getsweeptime:

    .. cpp:function:: OcaStatus GetSweepTime(OcaTimeInterval &sweepTime, OcaTimeInterval &minSweepTime, OcaTimeInterval &maxSweepTime)

        Gets the value of the SweepTime property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.11``.

        :param OcaTimeInterval sweepTime: Output parameter.
        :param OcaTimeInterval minSweepTime: Output parameter.
        :param OcaTimeInterval maxSweepTime: Output parameter.

    .. _ocasignalgenerator_setsweeptime:

    .. cpp:function:: OcaStatus SetSweepTime(OcaTimeInterval sweepTime)

        Sets the value of the SweepTime property. The return value indicates whether the property was successfully set.

        This method has id ``4.12``.

        :param OcaTimeInterval sweepTime: Input parameter.

    .. _ocasignalgenerator_getsweeprepeat:

    .. cpp:function:: OcaStatus GetSweepRepeat(OcaBoolean &sweepRepeat)

        Gets the value of the SweepRepeat property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.13``.

        :param OcaBoolean sweepRepeat: Output parameter.

    .. _ocasignalgenerator_setsweeprepeat:

    .. cpp:function:: OcaStatus SetSweepRepeat(OcaBoolean sweepRepeat)

        Sets the value of the SweepRepeat property. The return value indicates whether the property was successfully set.

        This method has id ``4.14``.

        :param OcaBoolean sweepRepeat: Input parameter.

    .. _ocasignalgenerator_getgenerating:

    .. cpp:function:: OcaStatus GetGenerating(OcaBoolean &generating)

        Gets the value of the Generating property. The return value indicates whether the property was successfully retrieved.

        This method has id ``4.15``.

        :param OcaBoolean generating: Output parameter.

    .. _ocasignalgenerator_start:

    .. cpp:function:: OcaStatus Start()

        Starts the signal generator. The return value indicates whether the signal generator was successfully started.

        This method has id ``4.16``.


    .. _ocasignalgenerator_stop:

    .. cpp:function:: OcaStatus Stop()

        Stops the signal generator. The return value indicates whether the signal generator was successfully stopped.

        This method has id ``4.17``.


    .. _ocasignalgenerator_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency1, OcaFrequency Frequency2, OcaDBz Level, OcaWaveformType Waveform, OcaSweepType SweepType, OcaTimeInterval SweepTime, OcaBoolean SweepRepeat)

        Sets some or all signal generation parameters. The return value indicates if the parameters were successfully set. The action of this method is atomic - if any of the value changes fails, none of the changes are made.

        This method has id ``4.18``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency1: Input parameter.
        :param OcaFrequency Frequency2: Input parameter.
        :param OcaDBz Level: Input parameter.
        :param OcaWaveformType Waveform: Input parameter.
        :param OcaSweepType SweepType: Input parameter.
        :param OcaTimeInterval SweepTime: Input parameter.
        :param OcaBoolean SweepRepeat: Input parameter.


    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


