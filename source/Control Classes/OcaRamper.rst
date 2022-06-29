.. _ocaramper:

1.2.3  OcaRamper
================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaRamper <ocaramper>` 

.. cpp:class:: OcaRamper: OcaAgent

    Agent that gradually changes a property setting from one value to another. Works on a scalar numeric or boolean property of a specified object. Does not work for array, list, map, struct, or string properties. Contains timer features to allow ramps to start immediately or at any time in the future. This is a weakly typed class. All ramping parameters are specified as a  **OcaFloat64** numbers.  
    
     - For unsigned integer targets, the ramping parameters are coerced to  **OcaUint64** before comparing.
     
    
     - For signed integer targets, the ramping parameters are coerced to  **OcaInt64** before comparing.
     
    
     - For boolean values, the the ramping parameters are coerced to  **OcaUint8.** True is assigned the value One, False is assigned the value Zero.
     

    **Properties**:

    .. _ocaramper_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.3"

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocaramper_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocaramper_state:

    .. cpp:member:: OcaRamperState State

        {Ready, Ramping, Paused, Completed, Disabled} Readonly.

        This property has id ``3.1``.

    .. _ocaramper_rampedproperty:

    .. cpp:member:: OcaProperty RampedProperty

        Identification of the property being ramped.

        This property has id ``3.2``.

    .. _ocaramper_timemode:

    .. cpp:member:: OcaTimeMode TimeMode = Relative

        Absolute or Relative time.

        This property has id ``3.3``.

    .. _ocaramper_starttime:

    .. cpp:member:: OcaTimeNTP StartTime

        Time at which to start ramp. If  **TimeMode=Relative** , the actual event start time equals the value of  **StartTime**  plus the absolute time that  **StartTime**  was most recently set. If  **TimeMode=Absolute** , the actual event start time equals the value of  **StartTime** 

        This property has id ``3.4``.

    .. _ocaramper_duration:

    .. cpp:member:: OcaTimeInterval Duration

        Duration of ramp period.

        This property has id ``3.5``.

    .. _ocaramper_interpolationlaw:

    .. cpp:member:: OcaRamperInterpolationLaw InterpolationLaw

        Ramper interpolation law

        This property has id ``3.6``.

    .. _ocaramper_goal:

    .. cpp:member:: OcaFloat64 Goal

        Final value of ramp. Datatype is target property's datatype.

        This property has id ``3.7``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocaramper_control:

    .. cpp:function:: OcaStatus Control(OcaRamperCommand Command)

        Executes the given ramper command. The return value indicates whether the command was successfully executed.

        This method has id ``3.1``.

        :param OcaRamperCommand Command: Input parameter.

    .. _ocaramper_getstate:

    .. cpp:function:: OcaStatus GetState(OcaRamperState &State)

        Gets current state of ramper. The return value indicates whether the state was successfully retrieved.

        This method has id ``3.2``.

        :param OcaRamperState State: Output parameter.

    .. _ocaramper_getrampedproperty:

    .. cpp:function:: OcaStatus GetRampedProperty(OcaProperty &property)

        Gets definition of ramped property. The return value indicates whether the object number was successfully retrieved.

        This method has id ``3.3``.

        :param OcaProperty property: Output parameter.

    .. _ocaramper_setrampedproperty:

    .. cpp:function:: OcaStatus SetRampedProperty(OcaProperty property)

        Defines property to be ramped. The return value indicates whether the definition was successful.

        This method has id ``3.4``.

        :param OcaProperty property: Input parameter.

    .. _ocaramper_gettimemode:

    .. cpp:function:: OcaStatus GetTimeMode(OcaTimeMode &TimeMode)

        Gets ramper time mode (absolute or relative). The return value indicates whether the time mode was successfully retrieved.

        This method has id ``3.5``.

        :param OcaTimeMode TimeMode: Output parameter.

    .. _ocaramper_settimemode:

    .. cpp:function:: OcaStatus SetTimeMode(OcaTimeMode TimeMode)

        Sets ramper time mode (absolute or relative). The return value indicates whether the time mode was successfully set.

        This method has id ``3.6``.

        :param OcaTimeMode TimeMode: Input parameter.

    .. _ocaramper_getstarttime:

    .. cpp:function:: OcaStatus GetStartTime(OcaTimeNTP &StartTime)

        Gets ramp start time. The return value indicates whether the start time was successfully retrieved.

        This method has id ``3.7``.

        :param OcaTimeNTP StartTime: Output parameter.

    .. _ocaramper_setstarttime:

    .. cpp:function:: OcaStatus SetStartTime(OcaTimeNTP TimeMode)

        Sets ramper start time. The return value indicates whether the start time was successfully set.

        This method has id ``3.8``.

        :param OcaTimeNTP TimeMode: Input parameter.

    .. _ocaramper_getduration:

    .. cpp:function:: OcaStatus GetDuration(OcaTimeInterval &Duration, OcaTimeInterval &miinDuration, OcaTimeInterval &maxDuration)

        Gets ramp duration. The return value indicates whether the duration was successfully retrieved.

        This method has id ``3.9``.

        :param OcaTimeInterval Duration: Output parameter.
        :param OcaTimeInterval miinDuration: Output parameter.
        :param OcaTimeInterval maxDuration: Output parameter.

    .. _ocaramper_setduration:

    .. cpp:function:: OcaStatus SetDuration(OcaTimeInterval Duration)

        Sets ramp duration. The return value indicates whether the duration was successfully set.

        This method has id ``3.10``.

        :param OcaTimeInterval Duration: Input parameter.

    .. _ocaramper_getinterpolationlaw:

    .. cpp:function:: OcaStatus GetInterpolationLaw(OcaRamperInterpolationLaw &law)

        Retrieves interpolation law setting. The return value indicates whether the setting was successfully retrieved.

        This method has id ``3.11``.

        :param OcaRamperInterpolationLaw law: Output parameter.

    .. _ocaramper_setinterpolationlaw:

    .. cpp:function:: OcaStatus SetInterpolationLaw(OcaRamperInterpolationLaw law)

        Sets ramp interpolation law. The return value indicates whether the law was successfully set.

        This method has id ``3.12``.

        :param OcaRamperInterpolationLaw law: Input parameter.

    .. _ocaramper_getgoal:

    .. cpp:function:: OcaStatus GetGoal(OcaFloat64 &goal)

        Retrieves ramp goal value. The return value indicates whether the duration was successfully retrieved.

        This method has id ``3.13``.

        :param OcaFloat64 goal: Output parameter.

    .. _ocaramper_setgoal:

    .. cpp:function:: OcaStatus SetGoal(OcaFloat64 goal)

        Sets ramp goal value. The return value indicates whether the duration was successfully set.

        This method has id ``3.14``.

        :param OcaFloat64 goal: Input parameter.


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
    
    


