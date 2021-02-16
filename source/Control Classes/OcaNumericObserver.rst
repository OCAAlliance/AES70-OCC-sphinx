.. _ocanumericobserver:

1.2.4  OcaNumericObserver
=========================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaNumericObserver: OcaAgent

    Observer of a scalar numeric or boolean property ("target property")
    of a specified object. Does not work for array, list, map, struct, or
    string properties. **OcaNumericObserver** emits an **Observation**
    event under certain conditions. There are three kinds of conditions:
    
    - **Numeric comparison** . The target property value meets a certain
    comparison condition. A selection of comparison operators is
    available. Such observations are called "asynchronous observations".
    
    
    - **Timer expiry** . The value of the **Period** property, if nonzero,
    is a the time interval for the recurrent timed emission of
    **Observation** events. Such events ("periodic observations") are
    emitted regardless of the target property's value.
    
    
    - **Combination of (1) and (2)** . If a numeric comparison and a
    nonzero period are both specified, then the **Observation** event is
    emitted when the timer expires **and** the numeric comparison is true.
    Such observations are called "conditional-periodic observations".
    This is a weakly typed class. Its threshold is specified as an
    **OcaFloat64** number.
    
    - For unsigned integer targets, the threshold and target are both
    coerced to **OcaUint64** before comparing.
    
    
    - For signed integer targets, the threshold and target are both
    coerced to **OcaInt64** before comparing.
    
    
    - For boolean values, the threshold hreshold and target are both
    coerced to **OcaUint8** , True is assigned the value One, False is
    assigned the value Zero.
    Note that this coercion may result in rounding errors if the observed
    datatype is of type OcaUint64 or OcaUint64. An **OcaNumericObserver**
    instance and the property it observes are bound at the time the
    **OcaNumericObserver** instance is constructed. For static devices,
    construction will occur during manufacture, or possibly during a
    subsequent hardware configuration step. For reconfigurable devices,
    construction might be done by online controllers as part of device
    configuration sessions. This class is normally used for monitoring
    readings of sensor readings, but may be used equally well for watching
    workers' parameter settings.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaObserverState State

        This property has id ``3.1``.

        State: triggered, not triggered

    .. cpp:member:: OcaProperty ObservedProperty

        This property has id ``3.2``.

        Identification of the property being observed.

    .. cpp:member:: OcaFloat64 Threshold

        This property has id ``3.3``.

        Comparison value for raising the **Triggered** event.

    .. cpp:member:: OcaRelationalOperator Operator

        This property has id ``3.4``.

        Relational operator used when comparing the value of the observed
        property to the threshold value.

    .. cpp:member:: OcaBoolean TwoWay

        This property has id ``3.5``.

        True to emit a **Triggered** event upon crossing the threshold in
        either direction; false to emit only upon crossing in the primary
        direction (i.e. rising when **Operator** is set to _GreaterThan_ or
        _GreaterThanOrEqual_ ; falling when **Operator** is set to _LessThan_
        or _LessThanOrEqual_ ; equality when **Operator** is set to _Equality_
        ; inequality when **Operator** is set to _Inequality_ ).

    .. cpp:member:: OcaFloat64 Hysteresis

        This property has id ``3.6``.

        Hysteresis that is used when observing the property value. This
        indicates which amount must be added/subtracted from the **Threshold**
        value to raise or re-enable the **Triggered** event of this
        **OcaObserver** object. The rules for hysteresis handling depend upon
        the configured **Operator** and **TwoWay** properties. The
        **Hysteresis** property is ignored if the **Operator** property is
        'Inequality'.

    .. cpp:member:: OcaTimeInterval Period

        This property has id ``3.7``.

        Repetition period or zero. If nonzero, the observer will retrieve the
        value and emit

    .. cpp:function:: OcaStatus GetLastObservation(OcaFloat64 &Observation)

        This method has id ``3.1``.

        Gets the value of the observed property that was reported by the most
        recently emitted Observation event. If the numeric observer has never
        emitted an Observation event, returns the IEEE not-a-number value. The
        return status indicates whether the value has been successfully
        returned.

        :param OcaFloat64 Observation: Output parameter.

    .. cpp:function:: OcaStatus GetState(OcaObserverState &state)

        This method has id ``3.2``.

        Gets the observer's state. The return value indicates whether the
        state was successfully retrieved.

        :param OcaObserverState state: Output parameter.

    .. cpp:function:: OcaStatus GetObservedProperty(OcaProperty &property)

        This method has id ``3.3``.

        Gets the identification of the property that the observer observes.
        The return value indicates whether the identification was successfully
        retrieved.

        :param OcaProperty property: Output parameter.

    .. cpp:function:: OcaStatus SetObservedProperty(OcaProperty property)

        This method has id ``3.4``.

        Sets the identification of the property that the observer observes.
        The return value indicates whether the identification was successfully
        set.

        :param OcaProperty property: Input parameter.

    .. cpp:function:: OcaStatus GetThreshold(OcaFloat64 &Threshold)

        This method has id ``3.5``.

        Gets the value of the **Threshold** property. The return value
        indicates whether the threshold value was successfully retrieved.

        :param OcaFloat64 Threshold: Output parameter.

    .. cpp:function:: OcaStatus SetThreshold(OcaFloat64 Threshold)

        This method has id ``3.6``.

        Sets the value of the **Threshold** property. The return value
        indicates whether the threshold value was successfully set.

        :param OcaFloat64 Threshold: Input parameter.

    .. cpp:function:: OcaStatus GetOperator(OcaRelationalOperator &operator)

        This method has id ``3.7``.

        Gets the value of the **Operator** property. The return value
        indicates whether the property was successfully retrieved.

        :param OcaRelationalOperator operator: Output parameter.

    .. cpp:function:: OcaStatus SetOperator(OcaRelationalOperator operator)

        This method has id ``3.8``.

        Sets the value of the **Operator** property. The return value
        indicates whether the operator was successfully set.

        :param OcaRelationalOperator operator: Input parameter.

    .. cpp:function:: OcaStatus GetTwoWay(OcaBoolean &twoWay)

        This method has id ``3.9``.

        Gets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean twoWay: Output parameter.

    .. cpp:function:: OcaStatus SetTwoWay(OcaBoolean twoWay)

        This method has id ``3.10``.

        Sets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully set.

        :param OcaBoolean twoWay: Input parameter.

    .. cpp:function:: OcaStatus GetHysteresis(OcaFloat64 &hysteresis)

        This method has id ``3.11``.

        Gets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully retrieved.

        :param OcaFloat64 hysteresis: Output parameter.

    .. cpp:function:: OcaStatus SetHysteresis(OcaFloat64 hysteresis)

        This method has id ``3.12``.

        Sets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully set.

        :param OcaFloat64 hysteresis: Input parameter.

    .. cpp:function:: OcaStatus GetPeriod(OcaTimeInterval &period)

        This method has id ``3.13``.

        Gets the value of the **Period** property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaTimeInterval period: Output parameter.

    .. cpp:function:: OcaStatus SetPeriod(OcaTimeInterval period)

        This method has id ``3.14``.

        Sets the value of the **Period** property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval period: Input parameter.

