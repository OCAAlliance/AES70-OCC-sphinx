.. _ocadynamics:

1.1.1.14  OcaDynamics
=====================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaDynamics <ocadynamics>` 

.. cpp:class:: OcaDynamics: OcaActuator

    A multipurpose dynamics processor. Can be configured as compressor,
    limiter, expander, or gate. This class is expected to handle the
    majority of the basic cases. More complex devices may be described in
    a different manner, using one or more **OcaDynamicsDetector** and
    **OcaDynamicsCurve** objects, in conjunction with other Worker objects
    as needed.

    **Properties**:

    .. _ocadynamics_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocadynamics_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocadynamics_triggered:

    .. cpp:member:: OcaBoolean Triggered

        Read-only property that indicates whether the dynamics processor is
        currently triggered (i.e. the signal level is above upper threshold or
        below lower threshold). This property can be monitored via a periodic
        event subscription.

        This property has id ``4.1``.

    .. _ocadynamics_dynamicgain:

    .. cpp:member:: OcaDB DynamicGain

        Current instantaneous gain of dynamics object. Readonly.

        This property has id ``4.2``.

    .. _ocadynamics_function:

    .. cpp:member:: OcaDynamicsFunction Function

        Dynamics element function - compressor, limiter, expander, etc.

        This property has id ``4.3``.

    .. _ocadynamics_ratio:

    .. cpp:member:: OcaFloat32 Ratio

        DEPRECATED PROPERTY - please use property **Slope** instead.
        Compression or expansion ratio. For Function = Compress or Limit,
        value is d(input amplitude)/d(output amplitude). For Function = Expand
        or Gate, value is d(output amplitude)/d(input amplitude).

        This property has id ``4.4``.

    .. _ocadynamics_threshold:

    .. cpp:member:: OcaDBr Threshold

        Compression or expansion threshold.

        This property has id ``4.5``.

    .. _ocadynamics_thresholdpresentationunits:

    .. cpp:member:: OcaPresentationUnit ThresholdPresentationUnits

        Compression or expansion threshold presentation units.

        This property has id ``4.6``.

    .. _ocadynamics_detectorlaw:

    .. cpp:member:: OcaLevelDetectionLaw DetectorLaw


        This property has id ``4.7``.

    .. _ocadynamics_attacktime:

    .. cpp:member:: OcaTimeInterval AttackTime

        Attack time in seconds.

        This property has id ``4.8``.

    .. _ocadynamics_releasetime:

    .. cpp:member:: OcaTimeInterval ReleaseTime

        Release time in seconds.

        This property has id ``4.9``.

    .. _ocadynamics_holdtime:

    .. cpp:member:: OcaTimeInterval HoldTime

        Hold time in seconds.

        This property has id ``4.10``.

    .. _ocadynamics_dynamicgainceiling:

    .. cpp:member:: OcaDB DynamicGainCeiling

        Upper limit for DynamicGain

        This property has id ``4.11``.

    .. _ocadynamics_dynamicgainfloor:

    .. cpp:member:: OcaDB DynamicGainFloor

        Lower limit for for DynamicGain

        This property has id ``4.12``.

    .. _ocadynamics_kneeparameter:

    .. cpp:member:: OcaFloat32 KneeParameter

        Soft knee parameter. Interpretation is device-dependent.

        This property has id ``4.13``.

    .. _ocadynamics_slope:

    .. cpp:member:: OcaFloat32 Slope

        Slope of transfer function = d(output amplitude) / d(input amplitude).
        See notes for class OcaDynamicsCurve for further detail. Note that the
        definition of this value does not depend on the value of property
        Function.

        This property has id ``4.14``.

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

    .. _ocadynamics_gettriggered:

    .. cpp:function:: OcaStatus GetTriggered(OcaBoolean &triggered)

        Gets the value of the Triggered property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.1``.

        :param OcaBoolean triggered: Output parameter.

    .. _ocadynamics_getdynamicgain:

    .. cpp:function:: OcaStatus GetDynamicGain(OcaDB &Gain)

        Gets the value of the DynamicGain property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.2``.

        :param OcaDB Gain: Output parameter.

    .. _ocadynamics_getfunction:

    .. cpp:function:: OcaStatus GetFunction(OcaDynamicsFunction &Func)

        Sets the value of the Function property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.3``.

        :param OcaDynamicsFunction Func: Output parameter.

    .. _ocadynamics_setfunction:

    .. cpp:function:: OcaStatus SetFunction(OcaDynamicsFunction Func)

        Sets the value of the Function property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.4``.

        :param OcaDynamicsFunction Func: Input parameter.

    .. _ocadynamics_getratio:

    .. cpp:function:: OcaStatus GetRatio(OcaFloat32 &Ratio, OcaFloat32 &minRatio, OcaFloat32 &maxRatio)

        Gets the value of the Ratio property. The return value indicates
        whether the property was successfully retrieved. GetRatio() is a
        DEPRECATED method. Please use **GetSlope()** instead.

        This method has id ``4.5``.

        :param OcaFloat32 Ratio: Output parameter.
        :param OcaFloat32 minRatio: Output parameter.
        :param OcaFloat32 maxRatio: Output parameter.

    .. _ocadynamics_setratio:

    .. cpp:function:: OcaStatus SetRatio(OcaFloat32 Ratio)

        Sets the value of the Ratio property. The return value indicates
        whether the property was successfully set. SetRatio() is a DEPRECATED
        method. Please use **SetSlope()** instead.

        This method has id ``4.6``.

        :param OcaFloat32 Ratio: Input parameter.

    .. _ocadynamics_getthreshold:

    .. cpp:function:: OcaStatus GetThreshold(OcaDBr &Threshold, OcaDBz &minThreshold, OcaDBz &maxThreshold)

        Gets the value of the Threshold property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.7``.

        :param OcaDBr Threshold: Output parameter.
        :param OcaDBz minThreshold: Output parameter.
        :param OcaDBz maxThreshold: Output parameter.

    .. _ocadynamics_setthreshold:

    .. cpp:function:: OcaStatus SetThreshold(OcaDBr threshold)

        Sets the value of the Threshold property. The return value indicates
        if the value was successfully set.

        This method has id ``4.8``.

        :param OcaDBr threshold: Input parameter.

    .. _ocadynamics_getthresholdpresentationunits:

    .. cpp:function:: OcaStatus GetThresholdPresentationUnits(OcaPresentationUnit &Units)

        Gets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully retrieved.

        This method has id ``4.9``.

        :param OcaPresentationUnit Units: Output parameter.

    .. _ocadynamics_setthresholdpresentationunits:

    .. cpp:function:: OcaStatus SetThresholdPresentationUnits(OcaPresentationUnit Units)

        Sets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully set.

        This method has id ``4.10``.

        :param OcaPresentationUnit Units: Input parameter.

    .. _ocadynamics_getdetectorlaw:

    .. cpp:function:: OcaStatus GetDetectorLaw(OcaLevelDetectionLaw &Law)

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        This method has id ``4.11``.

        :param OcaLevelDetectionLaw Law: Output parameter.

    .. _ocadynamics_setdetectorlaw:

    .. cpp:function:: OcaStatus SetDetectorLaw(OcaLevelDetectionLaw Law)

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        This method has id ``4.12``.

        :param OcaLevelDetectionLaw Law: Input parameter.

    .. _ocadynamics_getattacktime:

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the AttackTime property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.13``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamics_setattacktime:

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        Sets the value of the AttackTime property. The return value indicates
        if the value was successfully set.

        This method has id ``4.14``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamics_getreleasetime:

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the ReleaseTime property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.15``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamics_setreleasetime:

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        Sets the value of the ReleaseTime property. The return value indicates
        if the value was successfully set.

        This method has id ``4.16``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamics_getholdtime:

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the HoldTime property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.17``.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. _ocadynamics_setholdtime:

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        Sets the value of the HoldTime property. The return value indicates if
        the value was successfully set.

        This method has id ``4.18``.

        :param OcaTimeInterval Time: Input parameter.

    .. _ocadynamics_getdynamicgainfloor:

    .. cpp:function:: OcaStatus GetDynamicGainFloor(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        Gets the value of the DynamicGainFLoor property. The return value
        indicates if the value was successfully retrieved.

        This method has id ``4.19``.

        :param OcaDB Limit: Output parameter.
        :param OcaDB minLimit: Output parameter.
        :param OcaDB maxLimit: Output parameter.

    .. _ocadynamics_setdynamicgainfloor:

    .. cpp:function:: OcaStatus SetDynamicGainFloor(OcaDB Limit)

        Sets the value of the DynamicGainFloor property. The return value
        indicates if the value was successfully set.

        This method has id ``4.20``.

        :param OcaDB Limit: Input parameter.

    .. _ocadynamics_getdynamicgainceiling:

    .. cpp:function:: OcaStatus GetDynamicGainCeiling(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        Gets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully retrieved.

        This method has id ``4.21``.

        :param OcaDB Limit: Output parameter.
        :param OcaDB minLimit: Output parameter.
        :param OcaDB maxLimit: Output parameter.

    .. _ocadynamics_setdynamicgainceiling:

    .. cpp:function:: OcaStatus SetDynamicGainCeiling(OcaDB Limit)

        Sets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully set.

        This method has id ``4.22``.

        :param OcaDB Limit: Input parameter.

    .. _ocadynamics_getkneeparameter:

    .. cpp:function:: OcaStatus GetKneeParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        Gets the value of the KneeParameter property. The return value
        indicates if the value was successfully retrieved.

        This method has id ``4.23``.

        :param OcaFloat32 Parameter: Output parameter.
        :param OcaFloat32 minParameter: Output parameter.
        :param OcaFloat32 maxParameter: Output parameter.

    .. _ocadynamics_setkneeparameter:

    .. cpp:function:: OcaStatus SetKneeParameter(OcaFloat32 Parameter)

        Sets the value of the KneeParameter property. The return value
        indicates if the value was successfully set.

        This method has id ``4.24``.

        :param OcaFloat32 Parameter: Input parameter.

    .. _ocadynamics_getslope:

    .. cpp:function:: OcaStatus GetSlope(OcaFloat32 &Slope, OcaFloat32 &minSlope, OcaFloat32 &maxSlope)

        Gets the value of the Slope property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.25``.

        :param OcaFloat32 Slope: Output parameter.
        :param OcaFloat32 minSlope: Output parameter.
        :param OcaFloat32 maxSlope: Output parameter.

    .. _ocadynamics_setslope:

    .. cpp:function:: OcaStatus SetSlope(OcaFloat32 Slope)

        Sets the value of the Slope property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.26``.

        :param OcaFloat32 Slope: Input parameter.

    .. _ocadynamics_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaDynamicsFunction Function, OcaDBr Threshold, OcaPresentationUnit ThresholdPresentationUnits, OcaLevelDetectionLaw DetectorLaw, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime, OcaDB DynamicGainCeiling, OcaDB DynamicGainFloor, OcaFloat32 Slope, OcaFloat32 KneeParameter)

        Sets some or all dynamics parameters. The return value indicates if
        the parameters were successfully set. The action of this method is
        atomic - if any of the value changes fails, none of the changes are
        made.

        This method has id ``4.27``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaDynamicsFunction Function: Input parameter.
        :param OcaDBr Threshold: Input parameter.
        :param OcaPresentationUnit ThresholdPresentationUnits: Input parameter.
        :param OcaLevelDetectionLaw DetectorLaw: Input parameter.
        :param OcaTimeInterval AttackTime: Input parameter.
        :param OcaTimeInterval ReleaseTime: Input parameter.
        :param OcaTimeInterval HoldTime: Input parameter.
        :param OcaDB DynamicGainCeiling: Input parameter.
        :param OcaDB DynamicGainFloor: Input parameter.
        :param OcaFloat32 Slope: Input parameter.
        :param OcaFloat32 KneeParameter: Input parameter.


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
    
    


