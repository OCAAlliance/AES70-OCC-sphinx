.. _ocadynamics:

1.1.1.14  OcaDynamics
=====================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaDynamics: OcaActuator

    A multipurpose dynamics processor. Can be configured as compressor,
    limiter, expander, or gate. This class is expected to handle the
    majority of the basic cases. More complex devices may be described in
    a different manner, using one or more **OcaDynamicsDetector** and
    **OcaDynamicsCurve** objects, in conjunction with other Worker objects
    as needed.

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

    .. cpp:member:: OcaBoolean Triggered

        This property has id ``4.0``.

        Read-only property that indicates whether the dynamics processor is
        currently triggered (i.e. the signal level is above upper threshold or
        below lower threshold). This property can be monitored via a periodic
        event subscription.

    .. cpp:member:: OcaDB DynamicGain

        This property has id ``4.0``.

        Current instantaneous gain of dynamics object. Readonly.

    .. cpp:member:: OcaDynamicsFunction Function

        This property has id ``4.0``.

        Dynamics element function - compressor, limiter, expander, etc.

    .. cpp:member:: OcaFloat32 Ratio

        This property has id ``4.0``.

        DEPRECATED PROPERTY - please use property **Slope** instead.
        Compression or expansion ratio. For Function = Compress or Limit,
        value is d(input amplitude)/d(output amplitude). For Function = Expand
        or Gate, value is d(output amplitude)/d(input amplitude).

    .. cpp:member:: OcaDBr Threshold

        This property has id ``4.0``.

        Compression or expansion threshold.

    .. cpp:member:: OcaPresentationUnit ThresholdPresentationUnits

        This property has id ``4.0``.

        Compression or expansion threshold presentation units.

    .. cpp:member:: OcaLevelDetectionLaw DetectorLaw

        This property has id ``4.0``.


    .. cpp:member:: OcaTimeInterval AttackTime

        This property has id ``4.0``.

        Attack time in seconds.

    .. cpp:member:: OcaTimeInterval ReleaseTime

        This property has id ``4.0``.

        Release time in seconds.

    .. cpp:member:: OcaTimeInterval HoldTime

        This property has id ``4.0``.

        Hold time in seconds.

    .. cpp:member:: OcaDB DynamicGainCeiling

        This property has id ``4.0``.

        Upper limit for DynamicGain

    .. cpp:member:: OcaDB DynamicGainFloor

        This property has id ``4.0``.

        Lower limit for for DynamicGain

    .. cpp:member:: OcaFloat32 KneeParameter

        This property has id ``4.0``.

        Soft knee parameter. Interpretation is device-dependent.

    .. cpp:member:: OcaFloat32 Slope

        This property has id ``4.0``.

        Slope of transfer function = d(output amplitude) / d(input amplitude).
        See notes for class OcaDynamicsCurve for further detail. Note that the
        definition of this value does not depend on the value of property
        Function.

    .. cpp:function:: OcaStatus GetTriggered(OcaBoolean &triggered)

        This method has id ``4.1``.

        Gets the value of the Triggered property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean triggered: Output parameter.

    .. cpp:function:: OcaStatus GetDynamicGain(OcaDB &Gain)

        This method has id ``4.2``.

        Gets the value of the DynamicGain property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaDB Gain: Output parameter.

    .. cpp:function:: OcaStatus GetFunction(OcaDynamicsFunction &Func)

        This method has id ``4.3``.

        Sets the value of the Function property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaDynamicsFunction Func: Output parameter.

    .. cpp:function:: OcaStatus SetFunction(OcaDynamicsFunction Func)

        This method has id ``4.4``.

        Sets the value of the Function property. The return value indicates
        whether the property was successfully set.

        :param OcaDynamicsFunction Func: Input parameter.

    .. cpp:function:: OcaStatus GetRatio(OcaFloat32 &Ratio, OcaFloat32 &minRatio, OcaFloat32 &maxRatio)

        This method has id ``4.5``.

        Gets the value of the Ratio property. The return value indicates
        whether the property was successfully retrieved. GetRatio() is a
        DEPRECATED method. Please use **GetSlope()** instead.

        :param OcaFloat32 Ratio: Output parameter.
        :param OcaFloat32 minRatio: Output parameter.
        :param OcaFloat32 maxRatio: Output parameter.

    .. cpp:function:: OcaStatus SetRatio(OcaFloat32 Ratio)

        This method has id ``4.6``.

        Sets the value of the Ratio property. The return value indicates
        whether the property was successfully set. SetRatio() is a DEPRECATED
        method. Please use **SetSlope()** instead.

        :param OcaFloat32 Ratio: Input parameter.

    .. cpp:function:: OcaStatus GetThreshold(OcaDBr &Threshold, OcaDBz &minThreshold, OcaDBz &maxThreshold)

        This method has id ``4.7``.

        Gets the value of the Threshold property. The return value indicates
        if the value was successfully retrieved.

        :param OcaDBr Threshold: Output parameter.
        :param OcaDBz minThreshold: Output parameter.
        :param OcaDBz maxThreshold: Output parameter.

    .. cpp:function:: OcaStatus SetThreshold(OcaDBr threshold)

        This method has id ``4.8``.

        Sets the value of the Threshold property. The return value indicates
        if the value was successfully set.

        :param OcaDBr threshold: Input parameter.

    .. cpp:function:: OcaStatus GetThresholdPresentationUnits(OcaPresentationUnit &Units)

        This method has id ``4.9``.

        Gets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully retrieved.

        :param OcaPresentationUnit Units: Output parameter.

    .. cpp:function:: OcaStatus SetThresholdPresentationUnits(OcaPresentationUnit Units)

        This method has id ``4.10``.

        Sets the value of the ThresholdPresentationUnits property. The return
        value indicates if the value was successfully set.

        :param OcaPresentationUnit Units: Input parameter.

    .. cpp:function:: OcaStatus GetDetectorLaw(OcaLevelDetectionLaw &Law)

        This method has id ``4.11``.

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        :param OcaLevelDetectionLaw Law: Output parameter.

    .. cpp:function:: OcaStatus SetDetectorLaw(OcaLevelDetectionLaw Law)

        This method has id ``4.12``.

        Sets the value of the DetectorLaw property. The return value indicates
        if the value was successfully set.

        :param OcaLevelDetectionLaw Law: Input parameter.

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.13``.

        Gets the value of the AttackTime property. The return value indicates
        if the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        This method has id ``4.14``.

        Sets the value of the AttackTime property. The return value indicates
        if the value was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.15``.

        Gets the value of the ReleaseTime property. The return value indicates
        if the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        This method has id ``4.16``.

        Sets the value of the ReleaseTime property. The return value indicates
        if the value was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.17``.

        Gets the value of the HoldTime property. The return value indicates if
        the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        This method has id ``4.18``.

        Sets the value of the HoldTime property. The return value indicates if
        the value was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus GetDynamicGainFloor(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        This method has id ``4.19``.

        Gets the value of the DynamicGainFLoor property. The return value
        indicates if the value was successfully retrieved.

        :param OcaDB Limit: Output parameter.
        :param OcaDB minLimit: Output parameter.
        :param OcaDB maxLimit: Output parameter.

    .. cpp:function:: OcaStatus SetDynamicGainFloor(OcaDB Limit)

        This method has id ``4.20``.

        Sets the value of the DynamicGainFloor property. The return value
        indicates if the value was successfully set.

        :param OcaDB Limit: Input parameter.

    .. cpp:function:: OcaStatus GetDynamicGainCeiling(OcaDB &Limit, OcaDB &minLimit, OcaDB &maxLimit)

        This method has id ``4.21``.

        Gets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully retrieved.

        :param OcaDB Limit: Output parameter.
        :param OcaDB minLimit: Output parameter.
        :param OcaDB maxLimit: Output parameter.

    .. cpp:function:: OcaStatus SetDynamicGainCeiling(OcaDB Limit)

        This method has id ``4.22``.

        Sets the value of the DynamicGainCeiling property. The return value
        indicates if the value was successfully set.

        :param OcaDB Limit: Input parameter.

    .. cpp:function:: OcaStatus GetKneeParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        This method has id ``4.23``.

        Gets the value of the KneeParameter property. The return value
        indicates if the value was successfully retrieved.

        :param OcaFloat32 Parameter: Output parameter.
        :param OcaFloat32 minParameter: Output parameter.
        :param OcaFloat32 maxParameter: Output parameter.

    .. cpp:function:: OcaStatus SetKneeParameter(OcaFloat32 Parameter)

        This method has id ``4.24``.

        Sets the value of the KneeParameter property. The return value
        indicates if the value was successfully set.

        :param OcaFloat32 Parameter: Input parameter.

    .. cpp:function:: OcaStatus GetSlope(OcaFloat32 &Slope, OcaFloat32 &minSlope, OcaFloat32 &maxSlope)

        This method has id ``4.25``.

        Gets the value of the Slope property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaFloat32 Slope: Output parameter.
        :param OcaFloat32 minSlope: Output parameter.
        :param OcaFloat32 maxSlope: Output parameter.

    .. cpp:function:: OcaStatus SetSlope(OcaFloat32 Slope)

        This method has id ``4.26``.

        Sets the value of the Slope property. The return value indicates
        whether the property was successfully set.

        :param OcaFloat32 Slope: Input parameter.

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaDynamicsFunction Function, OcaDBr Threshold, OcaPresentationUnit ThresholdPresentationUnits, OcaLevelDetectionLaw DetectorLaw, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime, OcaDB DynamicGainCeiling, OcaDB DynamicGainFloor, OcaFloat32 Slope, OcaFloat32 KneeParameter)

        This method has id ``4.27``.

        Sets some or all dynamics parameters. The return value indicates if
        the parameters were successfully set. The action of this method is
        atomic - if any of the value changes fails, none of the changes are
        made.

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

