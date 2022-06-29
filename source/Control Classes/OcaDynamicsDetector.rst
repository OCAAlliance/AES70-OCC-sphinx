.. _ocadynamicsdetector:

1.1.1.15  OcaDynamicsDetector
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaDynamicsDetector <ocadynamicsdetector>` 

.. cpp:class:: OcaDynamicsDetector: OcaActuator

    Dynamics element : side-chain detector.

    **Properties**:

    .. _ocadynamicsdetector_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.15"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocadynamicsdetector_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocadynamicsdetector_law:

    .. cpp:member:: OcaLevelDetectionLaw Law

        Level detection law: RMS, Peak, possibly others

        This property has id ``4.1``.

    .. _ocadynamicsdetector_attacktime:

    .. cpp:member:: OcaTimeInterval AttackTime

        Detector attack time in seconds.

        This property has id ``4.2``.

    .. _ocadynamicsdetector_releasetime:

    .. cpp:member:: OcaTimeInterval ReleaseTime

        Detector release time in seconds.

        This property has id ``4.3``.

    .. _ocadynamicsdetector_holdtime:

    .. cpp:member:: OcaTimeInterval HoldTime

        Detector hold time in seconds.

        This property has id ``4.4``.

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

    .. _ocadynamicsdetector_getlaw:

    .. cpp:function:: OcaStatus GetLaw(OcaLevelDetectionLaw &Law)

        Gets the value of the Law property. Return status indicates whether the value was successfully retrieved.

        This method has id ``4.1``.

        :param OcaLevelDetectionLaw Law: Output parameter.

    .. _ocadynamicsdetector_setlaw:

    .. cpp:function:: OcaStatus SetLaw(OcaLevelDetectionLaw Law)

        Sets the value of the Law property. Return status indicates whether the value was successfully set.

        This method has id ``4.2``.

        :param OcaLevelDetectionLaw Law: Input parameter.

    .. _ocadynamicsdetector_getattacktime:

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the AttackTime property. The return value indicates if the value was successfully retrieved.

        This method has id ``4.3``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamicsdetector_setattacktime:

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        Sets the value of the AttackTime property. The return value indicates whether the property was successfully set.

        This method has id ``4.4``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamicsdetector_getreleasetime:

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the ReleaseTime property. The return value indicates if the value was successfully retrieved.

        This method has id ``4.5``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamicsdetector_setreleasetime:

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        Sets the value of the ReleaseTime property. The return value indicates whether the property was successfully set.

        This method has id ``4.6``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamicsdetector_getholdtime:

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the HoldTime property. The return value indicates if the value was successfully retrieved.

        This method has id ``4.7``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamicsdetector_setholdtime:

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        Sets the value of the HoldTime property. The return value indicates whether the property was successfully set.

        This method has id ``4.8``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamicsdetector_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaLevelDetectionLaw Law, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime)

        Sets some or all detector parameters. The return value indicates if the parameters were successfully set. The action of this method is atomic - if any of the value changes fails, none of the changes are made.

        This method has id ``4.9``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaLevelDetectionLaw Law: Input parameter.
        :param OcaTimeInterval AttackTime: Input parameter.
        :param OcaTimeInterval ReleaseTime: Input parameter.
        :param OcaTimeInterval HoldTime: Input parameter.


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
    
    


