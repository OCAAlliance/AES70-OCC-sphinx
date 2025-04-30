.. _ocanumericobserverlist:

1.2.9  OcaNumericObserverList
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaNumericObserverList <ocanumericobserverlist>`

.. cpp:class:: OcaNumericObserverList: OcaAgent

    Observer of a scalar numeric or boolean property ("target property") of a
    set of specified objects. This class is a subclass of
    **OcaNumericObserver**, and differs from that class only in that it observes
    a set of properties rather than a single property. Does not work for array,
    list, map, struct, or string properties. **OcaNumericObserverList** emits an
    **Observation** event under certain conditions. There are three kinds of
    conditions:

     - **Numeric comparison**. A target property value meets a certain
       comparison condition. A selection of comparison operators is available.
       Such observations are called "asynchronous observations".

     - **Timer expiry**. The value of the** Period** property, if nonzero, is a
       the time interval for the recurrent timed emission of **Observation**
       events. Such events ("periodic observations") are emitted regardless of
       the target property's value.

     - **Combination of (1) and (2)**. If a numeric comparison and a nonzero
       period are both specified, then the **Observation** event is emitted when
       the timer expires **and** the numeric comparison is true for at least one
       of the observed properties. Such observations are called
       "conditional-periodic observations".


    This is a weakly typed class. Its threshold is specified as an
    **OcaFloat64** number.

     - For unsigned integer targets, the threshold and target are both coerced
       to **OcaUint64** before comparing.

     - For signed integer targets, the threshold and target are both coerced to
       **OcaInt64** before comparing.

     - For boolean values, the threshold hreshold and target are both coerced to
       **OcaUint8**, True is assigned the value One, False is assigned the value
       Zero.


    Note that this coercion may result in rounding errors if the observed
    datatype is of type OcaUint64 or OcaUint64. An **OcaNumericObserver**
    instance and the property it observes are bound at the time the
    **OcaNumericObserver** instance is constructed. For static devices,
    construction will occur during manufacture, or possibly during a subsequent
    hardware configuration step. For reconfigurable devices, construction might
    be done by online controllers as part of device configuration sessions. This
    class is normally used for monitoring readings of sensor readings, but may
    be used equally well for watching workers' parameter settings.

    **Properties**:


    .. _ocanumericobserverlist_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.9"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocanumericobserverlist_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocanumericobserverlist_state:

    .. cpp:member:: OcaObserverState State

        State: triggered, not triggered

        This property has id ``3.1``.

    .. _ocanumericobserverlist_observedproperties:

    .. cpp:member:: OcaList<OcaProperty> ObservedProperties

        List of identifiers of the properties are being observed.

        This property has id ``3.2``.

    .. _ocanumericobserverlist_threshold:

    .. cpp:member:: OcaFloat64 Threshold

        Comparison value for raising the **Triggered** event.

        This property has id ``3.3``.

    .. _ocanumericobserverlist_operator:

    .. cpp:member:: OcaRelationalOperator Operator

        Relational operator used when comparing the value of the observed
        property to the threshold value.

        This property has id ``3.4``.

    .. _ocanumericobserverlist_twoway:

    .. cpp:member:: OcaBoolean TwoWay

        True to emit a **Triggered** event upon crossing the threshold in either
        direction; false to emit only upon crossing in the primary direction
        (i.e. rising when **Operator** is set to GreaterThan or
        GreaterThanOrEqual; falling when **Operator** is set to LessThan **** or
        LessThanOrEqual; equality when **Operator** is set to Equality;
        inequality when **Operator** is set to Inequality).

        This property has id ``3.5``.

    .. _ocanumericobserverlist_hysteresis:

    .. cpp:member:: OcaFloat64 Hysteresis

        Hysteresis that is used when observing the property value. This
        indicates which amount must be added/subtracted from the **Threshold**
        value to raise or re-enable the **Triggered** event of this
        **OcaObserver** object. The rules for hysteresis handling depend upon
        the configured **Operator** and **TwoWay** properties. The
        **Hysteresis** property is ignored if the **Operator** property is
        'Inequality'. If the State is **Not Triggered** it changes to
        **Triggered** if any of the ObservedProperties reaches the Threshold. If
        the State is **Triggered** it changes to **Not Triggered** only if all
        of the ObservedProperties no longer meet the ‘Threshold including
        Hysteresis’** .**

        This property has id ``3.6``.

    .. _ocanumericobserverlist_period:

    .. cpp:member:: OcaTimeInterval Period

        Repetition period or zero. If nonzero, the observer will retrieve the
        value and emit

        This property has id ``3.7``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocanumericobserverlist_getlastobservation:

    .. cpp:function:: OcaStatus GetLastObservation(OcaList<OcaFloat64> &Observation)

        Gets the values of the observed property that were reported by the most
        recently emitted Observation event. If the numeric observer has never
        emitted an Observation event, returns a list of IEEE not-a-number
        values. The order of values in the returned list is determined by the
        order of values set by SetObservedProperties, and is the same as the
        order of values returned by the Observation event, and the same as the
        order of object identifications returned by GetObservedProperties. The
        return status indicates whether the value has been successfully
        returned.

        This method has id ``3.1``.

        - :cpp:expr:`Observation`: Output parameter.


    .. _ocanumericobserverlist_getstate:

    .. cpp:function:: OcaStatus GetState(OcaObserverState &state)

        Gets the observer's state. The return value indicates whether the state
        was successfully retrieved.

        This method has id ``3.2``.

        - :cpp:expr:`state`: Output parameter.


    .. _ocanumericobserverlist_getobservedproperties:

    .. cpp:function:: OcaStatus GetObservedProperties(OcaList<OcaProperty> &property)

        Gets the identifications of the properties that the observer observes.
        The order of property identifications in the returned list is determined
        by the order of property identifications set by SetObservedProperties,
        and is the same as the order of values returned by GetLastObservation
        and the Observation event. The return value indicates whether the
        identifications were successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`property`: Output parameter.


    .. _ocanumericobserverlist_setobservedproperties:

    .. cpp:function:: OcaStatus SetObservedProperties(OcaList<OcaProperty> property)

        Sets the identifications of the properties that the observer observes.
        The order of property identifications supplied determines the order of
        property identifications returned by GetObservedProperties and the order
        of values returned by GetLastObservation and the Observation event. The
        return value indicates whether the identifications were successfully
        set.

        This method has id ``3.4``.

        - :cpp:expr:`property`: Input parameter.


    .. _ocanumericobserverlist_getthreshold:

    .. cpp:function:: OcaStatus GetThreshold(OcaFloat64 &Threshold)

        Gets the value of the **Threshold** property. The return value indicates
        whether the threshold value was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`Threshold`: Output parameter.


    .. _ocanumericobserverlist_setthreshold:

    .. cpp:function:: OcaStatus SetThreshold(OcaFloat64 Threshold)

        Sets the value of the **Threshold** property. The return value indicates
        whether the threshold value was successfully set.

        This method has id ``3.6``.

        - :cpp:expr:`Threshold`: Input parameter.


    .. _ocanumericobserverlist_getoperator:

    .. cpp:function:: OcaStatus GetOperator(OcaRelationalOperator &_operator)

        Gets the value of the **Operator** property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.7``.

        - :cpp:expr:`_operator`: Output parameter.


    .. _ocanumericobserverlist_setoperator:

    .. cpp:function:: OcaStatus SetOperator(OcaRelationalOperator _operator)

        Sets the value of the **Operator** property. The return value indicates
        whether the operator was successfully set.

        This method has id ``3.8``.

        - :cpp:expr:`_operator`: Input parameter.


    .. _ocanumericobserverlist_gettwoway:

    .. cpp:function:: OcaStatus GetTwoWay(OcaBoolean &twoWay)

        Gets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.9``.

        - :cpp:expr:`twoWay`: Output parameter.


    .. _ocanumericobserverlist_settwoway:

    .. cpp:function:: OcaStatus SetTwoWay(OcaBoolean twoWay)

        Sets the value of the **TwoWay** property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.10``.

        - :cpp:expr:`twoWay`: Input parameter.


    .. _ocanumericobserverlist_gethysteresis:

    .. cpp:function:: OcaStatus GetHysteresis(OcaFloat64 &hysteresis)

        Gets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully retrieved.

        This method has id ``3.11``.

        - :cpp:expr:`hysteresis`: Output parameter.


    .. _ocanumericobserverlist_sethysteresis:

    .. cpp:function:: OcaStatus SetHysteresis(OcaFloat64 hysteresis)

        Sets the value of the **Hysteresis** property. The return value
        indicates whether the property was successfully set.

        This method has id ``3.12``.

        - :cpp:expr:`hysteresis`: Input parameter.


    .. _ocanumericobserverlist_getperiod:

    .. cpp:function:: OcaStatus GetPeriod(OcaTimeInterval &period)

        Gets the value of the **Period** property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.13``.

        - :cpp:expr:`period`: Output parameter.


    .. _ocanumericobserverlist_setperiod:

    .. cpp:function:: OcaStatus SetPeriod(OcaTimeInterval period)

        Sets the value of the **Period** property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.14``.

        - :cpp:expr:`period`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`


    **Events**:


    .. _ocanumericobserverlist_observation:

    .. cpp:function:: void Observation(OcaObservationListEventData eventData)

        Event emitted to signal an asynchronous, periodic, or
        conditional-periodic observation. This event returns the complete list
        of values being observed, regardless of which one(s) may have triggered
        it in the first place. The order of values in the returned list is
        determined by the order of values set by SetObservedProperties, and is
        the same as the order of values returned by GetLastObservation, and the
        same as the order of object identifications returned by
        GetObservedProperties.

        This event has id ``3.1``.
