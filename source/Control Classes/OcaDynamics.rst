.. _ocadynamics:

1.1.1.14  OcaDynamics
=====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaDynamics <ocadynamics>`

.. cpp:class:: OcaDynamics: OcaActuator

    A multipurpose dynamics processor. Can be configured as compressor, limiter,
    expander, or gate. This class is expected to handle the majority of the
    basic cases. More complex devices may be described in a different manner,
    using one or more **OcaDynamicsDetector** and **OcaDynamicsCurve** objects,
    in conjunction with other Worker objects as needed.

    **Properties**:


    .. _ocadynamics_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.14"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadynamics_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

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

        DEPRECATED PROPERTY - please use property **Slope** instead. Compression
        or expansion ratio. For Function = Compress or Limit, value is d(input
        amplitude)/d(output amplitude). For Function = Expand or Gate, value is
        d(output amplitude)/d(input amplitude).

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


    .. _ocadynamics_gettriggered:

    .. cpp:function:: OcaStatus GetTriggered(OcaBoolean &triggered)

        Gets the value of the Triggered property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.1``.

        - :cpp:expr:`triggered`: Output parameter.


    .. _ocadynamics_getdynamicgain:

    .. cpp:function:: OcaStatus GetDynamicGain(OcaDB &Gain)

        Gets the value of the DynamicGain property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.2``.

        - :cpp:expr:`Gain`: Output parameter.


    .. _ocadynamics_getfunction:

    .. cpp:function:: OcaStatus GetFunction(OcaDynamicsFunction &Func)

        Sets the value of the Function property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``4.3``.

        - :cpp:expr:`Func`: Output parameter.


    .. _ocadynamics_setfunction:

    .. cpp:function:: OcaStatus SetFunction(OcaDynamicsFunction Func)

        Sets the value of the Function property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.4``.

        - :cpp:expr:`Func`: Input parameter.


    .. _ocadynamics_getratio:

    .. cpp:function:: OcaStatus GetRatio(OcaFloat32 &Ratio, OcaFloat32 &minRatio, OcaFloat32 &maxRatio)

        Gets the value of the Ratio property. The return value indicates whether
        the property was successfully retrieved. GetRatio() is a DEPRECATED
        method. Please use **GetSlope()** instead.

        This method has id ``4.5``.

        - :cpp:expr:`Ratio`: Output parameter.


        - :cpp:expr:`minRatio`: Output parameter.


        - :cpp:expr:`maxRatio`: Output parameter.


    .. _ocadynamics_setratio:

    .. cpp:function:: OcaStatus SetRatio(OcaFloat32 Ratio)

        Sets the value of the Ratio property. The return value indicates whether
        the property was successfully set. SetRatio() is a DEPRECATED method.
        Please use **SetSlope()** instead.

        This method has id ``4.6``.

        - :cpp:expr:`Ratio`: Input parameter.


    .. _ocadynamics_getthreshold:

    .. cpp:function:: OcaStatus GetThreshold(OcaDBr &Threshold, OcaDBz &minThreshold, OcaDBz &maxThreshold)

        Gets the value of the Threshold property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.7``.

        - :cpp:expr:`Threshold`: Output parameter.


        - :cpp:expr:`minThreshold`: Output parameter.


        - :cpp:expr:`maxThreshold`: Output parameter.


    .. _ocadynamics_setthreshold:

    .. cpp:function:: OcaStatus SetThreshold(OcaDBr threshold)

        Sets the value of the Threshold property. The return value indicates if
        the value was successfully set.

        This method has id ``4.8``.

        - :cpp:expr:`threshold`: Input parameter.


    .. _ocadynamics_getthresholdpresentationunits:

    .. cpp:function:: OcaStatus GetThresholdPresentationUnits(OcaPresentationUnit &Units)

        Gets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully retrieved.

        This method has id ``4.9``.

        - :cpp:expr:`Units`: Output parameter.


    .. _ocadynamics_setthresholdpresentationunits:

    .. cpp:function:: OcaStatus SetThresholdPresentationUnits(OcaPresentationUnit Units)

        Sets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully set.

        This method has id ``4.10``.

        - :cpp:expr:`Units`: Input parameter.


    .. _ocadynamics_getdetectorlaw:

    .. cpp:function:: OcaStatus GetDetectorLaw(OcaLevelDetectionLaw &Law)

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        This method has id ``4.11``.

        - :cpp:expr:`Law`: Output parameter.


    .. _ocadynamics_setdetectorlaw:

    .. cpp:function:: OcaStatus SetDetectorLaw(OcaLevelDetectionLaw Law)

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        This method has id ``4.12``.

        - :cpp:expr:`Law`: Input parameter.


    .. _ocadynamics_getattacktime:

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the AttackTime property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.13``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamics_setattacktime:

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        Sets the value of the AttackTime property. The return value indicates if
        the value was successfully set.

        This method has id ``4.14``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamics_getreleasetime:

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the ReleaseTime property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.15``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamics_setreleasetime:

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        Sets the value of the ReleaseTime property. The return value indicates
        if the value was successfully set.

        This method has id ``4.16``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamics_getholdtime:

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the HoldTime property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.17``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamics_setholdtime:

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        Sets the value of the HoldTime property. The return value indicates if
        the value was successfully set.

        This method has id ``4.18``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamics_getdynamicgainfloor:

    .. cpp:function:: OcaStatus GetDynamicGainFloor(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        Gets the value of the DynamicGainFLoor property. The return value
        indicates if the value was successfully retrieved.

        This method has id ``4.19``.

        - :cpp:expr:`Limit`: Output parameter.


        - :cpp:expr:`minLimit`: Output parameter.


        - :cpp:expr:`maxLimit`: Output parameter.


    .. _ocadynamics_setdynamicgainfloor:

    .. cpp:function:: OcaStatus SetDynamicGainFloor(OcaDB Limit)

        Sets the value of the DynamicGainFloor property. The return value
        indicates if the value was successfully set.

        This method has id ``4.20``.

        - :cpp:expr:`Limit`: Input parameter.


    .. _ocadynamics_getdynamicgainceiling:

    .. cpp:function:: OcaStatus GetDynamicGainCeiling(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        Gets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully retrieved.

        This method has id ``4.21``.

        - :cpp:expr:`Limit`: Output parameter.


        - :cpp:expr:`minLimit`: Output parameter.


        - :cpp:expr:`maxLimit`: Output parameter.


    .. _ocadynamics_setdynamicgainceiling:

    .. cpp:function:: OcaStatus SetDynamicGainCeiling(OcaDB Limit)

        Sets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully set.

        This method has id ``4.22``.

        - :cpp:expr:`Limit`: Input parameter.


    .. _ocadynamics_getkneeparameter:

    .. cpp:function:: OcaStatus GetKneeParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        Gets the value of the KneeParameter property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.23``.

        - :cpp:expr:`Parameter`: Output parameter.


        - :cpp:expr:`minParameter`: Output parameter.


        - :cpp:expr:`maxParameter`: Output parameter.


    .. _ocadynamics_setkneeparameter:

    .. cpp:function:: OcaStatus SetKneeParameter(OcaFloat32 Parameter)

        Sets the value of the KneeParameter property. The return value indicates
        if the value was successfully set.

        This method has id ``4.24``.

        - :cpp:expr:`Parameter`: Input parameter.


    .. _ocadynamics_getslope:

    .. cpp:function:: OcaStatus GetSlope(OcaFloat32 &Slope, OcaFloat32 &minSlope, OcaFloat32 &maxSlope)

        Gets the value of the Slope property. The return value indicates whether
        the property was successfully retrieved.

        This method has id ``4.25``.

        - :cpp:expr:`Slope`: Output parameter.


        - :cpp:expr:`minSlope`: Output parameter.


        - :cpp:expr:`maxSlope`: Output parameter.


    .. _ocadynamics_setslope:

    .. cpp:function:: OcaStatus SetSlope(OcaFloat32 Slope)

        Sets the value of the Slope property. The return value indicates whether
        the property was successfully set.

        This method has id ``4.26``.

        - :cpp:expr:`Slope`: Input parameter.


    .. _ocadynamics_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaDynamicsFunction Function, OcaDBr Threshold, OcaPresentationUnit ThresholdPresentationUnits, OcaLevelDetectionLaw DetectorLaw, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime, OcaDB DynamicGainCeiling, OcaDB DynamicGainFloor, OcaFloat32 Slope, OcaFloat32 KneeParameter)

        Sets some or all dynamics parameters. The return value indicates if the
        parameters were successfully set. The action of this method is atomic -
        if any of the value changes fails, none of the changes are made.

        This method has id ``4.27``.

        - :cpp:expr:`Mask`: Input parameter.


        - :cpp:expr:`Function`: Input parameter.


        - :cpp:expr:`Threshold`: Input parameter.


        - :cpp:expr:`ThresholdPresentationUnits`: Input parameter.


        - :cpp:expr:`DetectorLaw`: Input parameter.


        - :cpp:expr:`AttackTime`: Input parameter.


        - :cpp:expr:`ReleaseTime`: Input parameter.


        - :cpp:expr:`HoldTime`: Input parameter.


        - :cpp:expr:`DynamicGainCeiling`: Input parameter.


        - :cpp:expr:`DynamicGainFloor`: Input parameter.


        - :cpp:expr:`Slope`: Input parameter.


        - :cpp:expr:`KneeParameter`: Input parameter.


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

