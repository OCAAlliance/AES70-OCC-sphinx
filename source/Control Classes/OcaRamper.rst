.. _ocaramper:

1.2.3  OcaRamper
================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaRamper: OcaAgent

    Agent that gradually changes a property setting from one value to
    another. Works on a scalar numeric or boolean property of a specified
    object. Does not work for array, list, map, struct, or string
    properties. Contains timer features to allow ramps to start
    immediately or at any time in the future. This is a weakly typed
    class. All ramping parameters are specified as a **OcaFloat64**
    numbers.
    
    - For unsigned integer targets, the ramping parameters are coerced to
    **OcaUint64** before comparing.
    
    
    - For signed integer targets, the ramping parameters are coerced to
    **OcaInt64** before comparing.
    
    
    - For boolean values, the the ramping parameters are coerced to
    **OcaUint8.** True is assigned the value One, False is assigned the
    value Zero.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaRamperState State

        This property has id ``3.1``.

        {Ready, Ramping, Paused, Completed, Disabled} Readonly.

    .. cpp:member:: OcaProperty RampedProperty

        This property has id ``3.2``.

        Identification of the property being ramped.

    .. cpp:member:: OcaTimeMode TimeMode

        This property has id ``3.3``.

        Absolute or Relative time.

    .. cpp:member:: OcaTimeNTP StartTime

        This property has id ``3.4``.

        Time at which to start ramp. If **TimeMode=Relative** , the actual
        event start time equals the value of **StartTime** plus the absolute
        time that **StartTime** was most recently set. If
        **TimeMode=Absolute** , the actual event start time equals the value
        of **StartTime**

    .. cpp:member:: OcaTimeInterval Duration

        This property has id ``3.5``.

        Duration of ramp period.

    .. cpp:member:: OcaRamperInterpolationLaw InterpolationLaw

        This property has id ``3.6``.

        Ramper interpolation law

    .. cpp:member:: OcaFloat64 Goal

        This property has id ``3.7``.

        Final value of ramp. Datatype is target property's datatype.

    .. cpp:function:: OcaStatus Control(OcaRamperCommand Command)

        This method has id ``3.1``.

        Executes the given ramper command. The return value indicates whether
        the command was successfully executed.

        :param OcaRamperCommand Command: Input parameter.

    .. cpp:function:: OcaStatus GetState(OcaRamperState &State)

        This method has id ``3.2``.

        Gets current state of ramper. The return value indicates whether the
        state was successfully retrieved.

        :param OcaRamperState State: Output parameter.

    .. cpp:function:: OcaStatus GetRampedProperty(OcaProperty &property)

        This method has id ``3.3``.

        Gets definition of ramped property. The return value indicates whether
        the object number was successfully retrieved.

        :param OcaProperty property: Output parameter.

    .. cpp:function:: OcaStatus SetRampedProperty(OcaProperty property)

        This method has id ``3.4``.

        Defines property to be ramped. The return value indicates whether the
        definition was successful.

        :param OcaProperty property: Input parameter.

    .. cpp:function:: OcaStatus GetTimeMode(OcaTimeMode &TimeMode)

        This method has id ``3.5``.

        Gets ramper time mode (absolute or relative). The return value
        indicates whether the time mode was successfully retrieved.

        :param OcaTimeMode TimeMode: Output parameter.

    .. cpp:function:: OcaStatus SetTimeMode(OcaTimeMode TimeMode)

        This method has id ``3.6``.

        Sets ramper time mode (absolute or relative). The return value
        indicates whether the time mode was successfully set.

        :param OcaTimeMode TimeMode: Input parameter.

    .. cpp:function:: OcaStatus GetStartTime(OcaTimeNTP &StartTime)

        This method has id ``3.7``.

        Gets ramp start time. The return value indicates whether the start
        time was successfully retrieved.

        :param OcaTimeNTP StartTime: Output parameter.

    .. cpp:function:: OcaStatus SetStartTime(OcaTimeNTP TimeMode)

        This method has id ``3.8``.

        Sets ramper start time. The return value indicates whether the start
        time was successfully set.

        :param OcaTimeNTP TimeMode: Input parameter.

    .. cpp:function:: OcaStatus GetDuration(OcaTimeInterval &Duration, OcaTimeInterval &miinDuration, OcaTimeInterval &maxDuration)

        This method has id ``3.9``.

        Gets ramp duration. The return value indicates whether the duration
        was successfully retrieved.

        :param OcaTimeInterval Duration: Output parameter.
        :param OcaTimeInterval miinDuration: Output parameter.
        :param OcaTimeInterval maxDuration: Output parameter.

    .. cpp:function:: OcaStatus SetDuration(OcaTimeInterval Duration)

        This method has id ``3.10``.

        Sets ramp duration. The return value indicates whether the duration
        was successfully set.

        :param OcaTimeInterval Duration: Input parameter.

    .. cpp:function:: OcaStatus GetInterpolationLaw(OcaRamperInterpolationLaw &law)

        This method has id ``3.11``.

        Retrieves interpolation law setting. The return value indicates
        whether the setting was successfully retrieved.

        :param OcaRamperInterpolationLaw law: Output parameter.

    .. cpp:function:: OcaStatus SetInterpolationLaw(OcaRamperInterpolationLaw law)

        This method has id ``3.12``.

        Sets ramp interpolation law. The return value indicates whether the
        law was successfully set.

        :param OcaRamperInterpolationLaw law: Input parameter.

    .. cpp:function:: OcaStatus GetGoal(OcaFloat64 &goal)

        This method has id ``3.13``.

        Retrieves ramp goal value. The return value indicates whether the
        duration was successfully retrieved.

        :param OcaFloat64 goal: Output parameter.

    .. cpp:function:: OcaStatus SetGoal(OcaFloat64 goal)

        This method has id ``3.14``.

        Sets ramp goal value. The return value indicates whether the duration
        was successfully set.

        :param OcaFloat64 goal: Input parameter.

