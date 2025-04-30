.. _ocaramper:

1.2.3  OcaRamper
================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaRamper <ocaramper>`

.. cpp:class:: OcaRamper: OcaAgent

    Agent that gradually changes a property setting from one value to another.
    Works on a scalar numeric or boolean property of a specified object. Does
    not work for array, list, map, struct, or string properties. Contains timer
    features to allow ramps to start immediately or at any time in the future.
    This is a weakly typed class. All ramping parameters are specified as a
    **OcaFloat64** numbers.

     - For unsigned integer targets, the ramping parameters are coerced to
       **OcaUint64** before comparing.

     - For signed integer targets, the ramping parameters are coerced to
       **OcaInt64** before comparing.

     - For boolean values, the the ramping parameters are coerced to
       **OcaUint8.** True is assigned the value One, False is assigned the value
       Zero.



    **Properties**:


    .. _ocaramper_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.3"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaramper_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaramper_duration:

    .. cpp:member:: OcaTimeInterval Duration

        Duration of ramp period.

        This property has id ``3.5``.

    .. _ocaramper_goal:

    .. cpp:member:: OcaFloat64 Goal

        Final value of ramp. Datatype is target property's datatype.

        This property has id ``3.7``.

    .. _ocaramper_interpolationlaw:

    .. cpp:member:: OcaRamperInterpolationLaw InterpolationLaw

        Ramper interpolation law

        This property has id ``3.6``.

    .. _ocaramper_rampedproperty:

    .. cpp:member:: OcaProperty RampedProperty

        Identification of the property being ramped.

        This property has id ``3.2``.

    .. _ocaramper_starttime:

    .. cpp:member:: OcaTimeNTP StartTime

        Time at which to start ramp. If **TimeMode=Relative**, the actual event
        start time equals the value of **StartTime** plus the absolute time that
        **StartTime** was most recently set. If **TimeMode=Absolute**, the
        actual event start time equals the value of **StartTime.** In version 3
        of this class, this property is **deprecated** and replaced by property
        **StartWhen**.

        This property has id ``3.4``.

    .. _ocaramper_startwhen:

    .. cpp:member:: OcaWhen StartWhen

        An **OcaWhen** item that specifies when to start ramp. Absolute or
        relative time, according to what the **OcaWhen** item specifies.
        Relative time values are based on the absolute time that **StartWhen**
        was most recently set.

        This property has id ``3.8``.

    .. _ocaramper_state:

    .. cpp:member:: OcaRamperState State

        {Ready, Ramping, Paused, Completed, Disabled} Readonly.

        This property has id ``3.1``.

    .. _ocaramper_timemode:

    .. cpp:member:: OcaTimeMode TimeMode

        Absolute or Relative time. In version 3 of this class, this property is
        **deprecated** and replaced by property **StartWhen**.

        This property has id ``3.3``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocaramper_control:

    .. cpp:function:: OcaStatus Control(OcaRamperCommand Command)

        Executes the given Ramper command. The return value indicates whether
        the command was successfully executed.

        This method has id ``3.1``.

        - :cpp:expr:`Command`: Input parameter.


    .. _ocaramper_getstate:

    .. cpp:function:: OcaStatus GetState(OcaRamperState &State)

        Gets current state of ramper. The return value indicates whether the
        state was successfully retrieved.

        This method has id ``3.2``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocaramper_getrampedproperty:

    .. cpp:function:: OcaStatus GetRampedProperty(OcaProperty &property)

        Gets definition of ramped property. The return value indicates whether
        the object number was successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`property`: Output parameter.


    .. _ocaramper_setrampedproperty:

    .. cpp:function:: OcaStatus SetRampedProperty(OcaProperty property)

        Defines property to be ramped. The return value indicates whether the
        definition was successful.

        This method has id ``3.4``.

        - :cpp:expr:`property`: Input parameter.


    .. _ocaramper_gettimemode:

    .. cpp:function:: OcaStatus GetTimeMode(OcaTimeMode &TimeMode)

        Gets ramper time mode (absolute or relative). **Deprecated** in v3 of
        this class.

        This method has id ``3.5``.

        - :cpp:expr:`TimeMode`: Output parameter.


    .. _ocaramper_settimemode:

    .. cpp:function:: OcaStatus SetTimeMode(OcaTimeMode TimeMode)

        Sets ramper time mode (absolute or relative). **Deprecated** in v3 of
        this class.

        This method has id ``3.6``.

        - :cpp:expr:`TimeMode`: Input parameter.


    .. _ocaramper_getstarttime:

    .. cpp:function:: OcaStatus GetStartTime(OcaTimeNTP &StartTime)

        Output parameter that holds the start time of the ramp if the method
        succeeds. **Deprecated** in version 3 of this class.

        This method has id ``3.7``.

        - :cpp:expr:`StartTime`: Output parameter.


    .. _ocaramper_setstarttime:

    .. cpp:function:: OcaStatus SetStartTime(OcaTimeNTP TimeMode)

        Sets ramper start time. **Deprecated** in v3 of this class.

        This method has id ``3.8``.

        - :cpp:expr:`TimeMode`: Input parameter.


    .. _ocaramper_getduration:

    .. cpp:function:: OcaStatus GetDuration(OcaTimeInterval &Duration, OcaTimeInterval &minDuration, OcaTimeInterval &maxDuration)

        Gets ramp duration. The return value indicates whether the duration was
        successfully retrieved.

        This method has id ``3.9``.

        - :cpp:expr:`Duration`: Output parameter.


        - :cpp:expr:`minDuration`: Output parameter.


        - :cpp:expr:`maxDuration`: Output parameter.


    .. _ocaramper_setduration:

    .. cpp:function:: OcaStatus SetDuration(OcaTimeInterval Duration)

        Sets ramp duration. The return value indicates whether the duration was
        successfully set.

        This method has id ``3.10``.

        - :cpp:expr:`Duration`: Input parameter.


    .. _ocaramper_getinterpolationlaw:

    .. cpp:function:: OcaStatus GetInterpolationLaw(OcaRamperInterpolationLaw &law)

        Retrieves interpolation law setting. The return value indicates whether
        the setting was successfully retrieved.

        This method has id ``3.11``.

        - :cpp:expr:`law`: Output parameter.


    .. _ocaramper_setinterpolationlaw:

    .. cpp:function:: OcaStatus SetInterpolationLaw(OcaRamperInterpolationLaw law)

        Sets ramp interpolation law. The return value indicates whether the law
        was successfully set.

        This method has id ``3.12``.

        - :cpp:expr:`law`: Input parameter.


    .. _ocaramper_getgoal:

    .. cpp:function:: OcaStatus GetGoal(OcaFloat64 &goal)

        Retrieves ramp goal value. The return value indicates whether the
        duration was successfully retrieved.

        This method has id ``3.13``.

        - :cpp:expr:`goal`: Output parameter.


    .. _ocaramper_setgoal:

    .. cpp:function:: OcaStatus SetGoal(OcaFloat64 goal)

        Sets ramp goal value. The return value indicates whether the duration
        was successfully set.

        This method has id ``3.14``.

        - :cpp:expr:`goal`: Input parameter.


    .. _ocaramper_getstartwhen:

    .. cpp:function:: OcaStatus GetStartWhen(OcaWhen &When)

        Gets the value of the **StartWhen** property.

        This method has id ``3.15``.

        - :cpp:expr:`When`: Output parameter.


    .. _ocaramper_setstartwhen:

    .. cpp:function:: OcaStatus SetStartWhen(OcaWhen When)

        Sets the value of the **StartWhen** property. Shall fail if called when
        **State** is **Ramping**.

        This method has id ``3.16``.

        - :cpp:expr:`When`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaAgent::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

