.. _ocadelayextended:

1.1.1.7.1  OcaDelayExtended
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaDelay <ocadelay>` :raw:html:`&rarr;` :ref:`OcaDelayExtended <ocadelayextended>` 

.. cpp:class:: OcaDelayExtended: OcaDelay

    Signal delay - extended version. Allows setting delay value in various units. Note that the inherited property 04p01 DelayTime is also supported by this class and reflects actual achieved delay in seconds.

    **Properties**:

    .. _ocadelayextended_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.7.1"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``5.1``.

    .. _ocadelayextended_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``5.2``.

    .. _ocadelayextended_delayvalue:

    .. cpp:member:: OcaDelayValue DelayValue

        Delay value.

        This property has id ``5.1``.

    Properties inherited from :ref:`OcaDelay <OcaDelay>`:
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaDelay::DelayTime <OcaDelay_DelayTime>`
    
    
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

    .. _ocadelayextended_getdelayvalue:

    .. cpp:function:: OcaStatus GetDelayValue(OcaDelayValue &Value, OcaDelayValue &minValue, OcaDelayValue &maxValue)

        Gets the value of the DelayValue property. The return value indicates whether the property was successfully retrieved.

        This method has id ``5.1``.

        :param OcaDelayValue Value: Output parameter.
        :param OcaDelayValue minValue: Output parameter.
        :param OcaDelayValue maxValue: Output parameter.

    .. _ocadelayextended_setdelayvalue:

    .. cpp:function:: OcaStatus SetDelayValue(OcaDelayValue Value)

        Sets the value of the DelayValue property. The return value indicates whether the property was successfully set.

        This method has id ``5.2``.

        :param OcaDelayValue Value: Input parameter.

    .. _ocadelayextended_getdelayvalueconverted:

    .. cpp:function:: OcaStatus GetDelayValueConverted(OcaDelayUnit UoM, OcaDelayValue &Value)

        Return current delay setting, converted to given units. The return value indicates whether the method has succeeded.

        This method has id ``5.3``.

        :param OcaDelayUnit UoM: Input parameter.
        :param OcaDelayValue Value: Output parameter.


    Methods inherited from :ref:`OcaDelay <OcaDelay>`:
    
    - :ref:`OcaDelay::GetDelayTime(Time, minTime, maxTime) <OcaDelay_GetDelayTime>`
    
    - :ref:`OcaDelay::SetDelayTime(delayTime) <OcaDelay_SetDelayTime>`
    
    
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
    
    


