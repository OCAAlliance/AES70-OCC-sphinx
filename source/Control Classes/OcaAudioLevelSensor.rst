.. _ocaaudiolevelsensor:

1.1.2.2.1  OcaAudioLevelSensor
==============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaSensor <ocasensor>` :raw:html:`&rarr;` :ref:`OcaLevelSensor <ocalevelsensor>` :raw:html:`&rarr;` :ref:`OcaAudioLevelSensor <ocaaudiolevelsensor>` 

.. cpp:class:: OcaAudioLevelSensor: OcaLevelSensor

    Child of  **OcaLevelSensor** that returns an audio meter reading in dB relative to a known reference level, and whose value has been calculated by the selected averaging algorithm.

    **Properties**:

    .. _ocaaudiolevelsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.2.1"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``5.1``.

    .. _ocaaudiolevelsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``5.2``.

    .. _ocaaudiolevelsensor_law:

    .. cpp:member:: OcaLevelMeterLaw Law

        Enum that defines metering algorithm, including averaging characteristics and, in some cases, reference level. Readonly in some objects.

        This property has id ``5.1``.

    Properties inherited from :ref:`OcaLevelSensor <OcaLevelSensor>`:
    
    - :cpp:texpr:`OcaDB` :ref:`OcaLevelSensor::Reading <OcaLevelSensor_Reading>`
    
    
    Properties inherited from :ref:`OcaSensor <OcaSensor>`:
    
    - :cpp:texpr:`OcaSensorReadingState` :ref:`OcaSensor::ReadingState <OcaSensor_ReadingState>`
    
    
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

    .. _ocaaudiolevelsensor_getlaw:

    .. cpp:function:: OcaStatus GetLaw(OcaLevelMeterLaw &law)

        Gets the value of the Law property. The return value indicates whether the property was successfully retrieved.

        This method has id ``5.1``.

        :param OcaLevelMeterLaw law: Output parameter.

    .. _ocaaudiolevelsensor_setlaw:

    .. cpp:function:: OcaStatus SetLaw(OcaLevelMeterLaw law)

        Sets the value of the Law property. The return value indicates whether the property was successfully set. Only implemented for objects whose Law property is read/write.

        This method has id ``5.2``.

        :param OcaLevelMeterLaw law: Input parameter.


    Methods inherited from :ref:`OcaLevelSensor <OcaLevelSensor>`:
    
    - :ref:`OcaLevelSensor::GetReading(Reading, minReading, maxReading) <OcaLevelSensor_GetReading>`
    
    
    Methods inherited from :ref:`OcaSensor <OcaSensor>`:
    
    - :ref:`OcaSensor::GetReadingState(state) <OcaSensor_GetReadingState>`
    
    
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
    
    


