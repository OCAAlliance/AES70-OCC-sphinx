.. _ocabitstringsensor:

1.1.2.1.13  OcaBitstringSensor
==============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaSensor <ocasensor>` :raw:html:`&rarr;` :ref:`OcaBasicSensor <ocabasicsensor>` :raw:html:`&rarr;` :ref:`OcaBitstringSensor <ocabitstringsensor>` 

.. cpp:class:: OcaBitstringSensor: OcaBasicSensor

    Bit string sensor.

    **Properties**:

    .. _ocabitstringsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.1.13"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``5.1``.

    .. _ocabitstringsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``5.2``.

    .. _ocabitstringsensor_bitstring:

    .. cpp:member:: OcaBitstring BitString

        The bitstring.

        This property has id ``5.1``.

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

    .. _ocabitstringsensor_getnrbits:

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &NrBits)

        Gets the number of bits of the bitmask data. Returned status indicates success or failure of the retrieval.

        This method has id ``5.1``.

        :param OcaUint16 NrBits: Output parameter.

    .. _ocabitstringsensor_getbit:

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaUint8 &bit)

        Gets the value of the given bit. Return status indicates success or failure of the retrieval.

        This method has id ``5.2``.

        :param OcaUint16 bitNr: Input parameter.
        :param OcaUint8 bit: Output parameter.

    .. _ocabitstringsensor_getbitstring:

    .. cpp:function:: OcaStatus GetBitString(OcaBitstring &BitString)

        Gets the entire bitstring. Return status indicates success or failure of the retrieval.

        This method has id ``5.3``.

        :param OcaBitstring BitString: Output parameter.


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
    
    


