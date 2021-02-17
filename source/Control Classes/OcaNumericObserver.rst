.. _ocanumericobserver:

1.2.4  OcaNumericObserver
=========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaNumericObserver <ocanumericobserver>` 

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

    **Properties**:

    .. _ocanumericobserver_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocanumericobserver_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocanumericobserver_state:

    .. cpp:member:: OcaObserverState State

        State: triggered, not triggered

        This property has id ``3.1``.

    .. _ocanumericobserver_observedproperty:

    .. cpp:member:: OcaProperty ObservedProperty

        Identification of the property being observed.

        This property has id ``3.2``.

    .. _ocanumericobserver_threshold:

    .. cpp:member:: OcaFloat64 Threshold

        Comparison value for raising the **Triggered** event.

        This property has id ``3.3``.

    .. _ocanumericobserver_operator:

    .. cpp:member:: OcaRelationalOperator Operator

        Relational operator used when comparing the value of the observed
        property to the threshold value.

        This property has id ``3.4``.

    .. _ocanumericobserver_twoway:

    .. cpp:member:: OcaBoolean TwoWay

        True to emit a **Triggered** event upon crossing the threshold in
        either direction; false to emit only upon crossing in the primary
        direction (i.e. rising when **Operator** is set to _GreaterThan_ or
        _GreaterThanOrEqual_ ; falling when **Operator** is set to _LessThan_
        or _LessThanOrEqual_ ; equality when **Operator** is set to _Equality_
        ; inequality when **Operator** is set to _Inequality_ ).

        This property has id ``3.5``.

    .. _ocanumericobserver_hysteresis:

    .. cpp:member:: OcaFloat64 Hysteresis

        Hysteresis that is used when observing the property value. This
        indicates which amount must be added/subtracted from the **Threshold**
        value to raise or re-enable the **Triggered** event of this
        **OcaObserver** object. The rules for hysteresis handling depend upon
        the configured **Operator** and **TwoWay** properties. The
        **Hysteresis** property is ignored if the **Operator** property is
        'Inequality'.

        This property has id ``3.6``.

    .. _ocanumericobserver_period:

    .. cpp:member:: OcaTimeInterval Period

        Repetition period or zero. If nonzero, the observer will retrieve the
        value and emit

        This property has id ``3.7``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocanumericobserver_getlastobservation:

    .. cpp:function:: OcaStatus GetLastObservation(OcaFloat64 &Observation)

        Gets the value of the observed property that was reported by the most
        recently emitted Observation event. If the numeric observer has never
        emitted an Observation event, returns the IEEE not-a-number value. The
        return status indicates whether the value has been successfully
        returned.

        This method has id ``3.1``.

        :param OcaFloat64 Observation: Output parameter.

    .. _ocanumericobserver_getstate:

    .. cpp:function:: OcaStatus GetState(OcaObserverState &state)

        Gets the observer's state. The return value indicates whether the
        state was successfully retrieved.

        This method has id ``3.2``.

        :param OcaObserverState state: Output parameter.

    .. _ocanumericobserver_getobservedproperty:

    .. cpp:function:: OcaStatus GetObservedProperty(OcaProperty &property)

        Gets the identification of the property that the observer observes.
        The return value indicates whether the identification was successfully
        retrieved.

        This method has id ``3.3``.

        :param OcaProperty property: Output parameter.

    .. _ocanumericobserver_setobservedproperty:

    .. cpp:function:: OcaStatus SetObservedProperty(OcaProperty property)

        Sets the identification of the property that the observer observes.
        The return value indicates whether the identification was successfully
        set.

        This method has id ``3.4``.

        :param OcaProperty property: Input parameter.

    .. _ocanumericobserver_getthreshold:

    .. cpp:function:: OcaStatus GetThreshold(OcaFloat64 &Threshold)

        Gets the value of the **Threshold** property. The return value
        indicates whether the threshold value was successfully retrieved.

        This method has id ``3.5``.

        :param OcaFloat64 Threshold: Output parameter.

    .. _ocanumericobserver_setthreshold:

    .. cpp:function:: OcaStatus SetThreshold(OcaFloat64 Threshold)

        Sets the value of the **Threshold** property. The return value
        indicates whether the threshold value was successfully set.

        This method has id ``3.6``.

        :param OcaFloat64 Threshold: Input parameter.

    .. _ocanumericobserver_getoperator:

    .. cpp:function:: OcaStatus GetOperator(OcaRelationalOperator &operator)

        Gets the value of the **Operator** property. The return value
        indicates whether the property was successfully retrieved.

        This method has id ``3.7``.

        :param OcaRelationalOperator operator: Output parameter.

    .. _ocanumericobserver_setoperator:

    .. cpp:function:: OcaStatus SetOperator(OcaRelationalOperator operator)

        Sets the value of the **Operator** property. The return value
        indicates whether the operator was successfully set.

        This method has id ``3.8``.

        :param OcaRelationalOperator operator: Input parameter.

    .. _ocanumericobserver_gettwoway:

    .. cpp:function:: OcaStatus GetTwoWay(OcaBoolean &twoWay)

        Gets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.9``.

        :param OcaBoolean twoWay: Output parameter.

    .. _ocanumericobserver_settwoway:

    .. cpp:function:: OcaStatus SetTwoWay(OcaBoolean twoWay)

        Sets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.10``.

        :param OcaBoolean twoWay: Input parameter.

    .. _ocanumericobserver_gethysteresis:

    .. cpp:function:: OcaStatus GetHysteresis(OcaFloat64 &hysteresis)

        Gets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully retrieved.

        This method has id ``3.11``.

        :param OcaFloat64 hysteresis: Output parameter.

    .. _ocanumericobserver_sethysteresis:

    .. cpp:function:: OcaStatus SetHysteresis(OcaFloat64 hysteresis)

        Sets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully set.

        This method has id ``3.12``.

        :param OcaFloat64 hysteresis: Input parameter.

    .. _ocanumericobserver_getperiod:

    .. cpp:function:: OcaStatus GetPeriod(OcaTimeInterval &period)

        Gets the value of the **Period** property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.13``.

        :param OcaTimeInterval period: Output parameter.

    .. _ocanumericobserver_setperiod:

    .. cpp:function:: OcaStatus SetPeriod(OcaTimeInterval period)

        Sets the value of the **Period** property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.14``.

        :param OcaTimeInterval period: Input parameter.


    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


    **Events**:

    .. _ocanumericobserver_observation:

    .. cpp:function:: void Observation(OcaObservationEventData eventData)

        Event emitted to signal an asynchronous, periodic, or
        conditional-periodic observation.


