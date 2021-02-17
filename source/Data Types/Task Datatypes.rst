**************
Task Datatypes
**************

.. _OcaTaskID:

OcaTaskID
=========

.. cpp:type:: OcaTaskID = OcaUint32

    ID of a Task (i.e. ID of an instance of the OcaTask datatype)
.. _OcaTaskGroupID:

OcaTaskGroupID
==============

.. cpp:type:: OcaTaskGroupID = OcaUint16

    ID of an OcaTaskGroup object.
.. _OcaTaskStatus:

OcaTaskStatus
=============

.. cpp:struct:: OcaTaskStatus
    
    Status of an OcaTask: task state plus a nonspecific blob named
    Parameter which the application can use, or not.
    
    - The initial value of Parameter is null.
    
    
    - The controller sets the value of Parameter via the Control() method.
    
    
    - If the task's state changes due to an internal event (examples: task
    duration value reached; or failure due to an error), Parameter is not
    changed.
    

    .. cpp:member:: OcaTaskID ID

        ID of the task to which this state descriptor applies.

    .. cpp:member:: OcaTaskState State

        State of the task - running, stopped, etc.

    .. cpp:member:: OcaUint16 ErrorCode

        Error code. Value is application-specific.


OCP.1 Encoding
--------------

========= =========== ===========
Field     Basic type  Byte length
========= =========== ===========
ID.Value  OcaUint32   4          
State     OcaEnumItem 1          
ErrorCode OcaUint16   2          
========= =========== ===========


.. _OcaTaskState:

OcaTaskState
============

.. cpp:enum:: OcaTaskState : uint8_t

    States of OcaTask object. State values change as a result of the
    object's having received a comment or encountering processing events
    (e.g. completion).

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.
    .. cpp:enumerator:: NotPrepared = 1

        Task is constructed but not initialized.
    .. cpp:enumerator:: Disabled = 2

        Task is initialized but not available to run.
    .. cpp:enumerator:: Enabled = 3

        Task is available for running.
    .. cpp:enumerator:: Running = 4

        Task is running.
    .. cpp:enumerator:: Completed = 5

        Task has terminated successfully.
    .. cpp:enumerator:: Failed = 6

        Task has terminated unsuccessfully.
    .. cpp:enumerator:: Stopped = 7

        Task was gracefully stopped by a **Stop** command.
    .. cpp:enumerator:: Aborted = 8

        Task was forcibly terminated by an **Abort** command.
.. _OcaTask:

OcaTask
=======

.. cpp:struct:: OcaTask
    
    An execution thread that runs an AES70 Program. Programs are
    OcaLibrary volumes that contain application-specific execution
    instructions.

    .. cpp:member:: OcaTaskID ID

        Task ID - assigned by OcaTaskManager

    .. cpp:member:: OcaString Label


    .. cpp:member:: OcaLibVolIdentifier ProgramID

        ID of program this task was given or null if it's idle.

    .. cpp:member:: OcaTaskGroupID GroupID

        ID of group the task is in, or zero if it isn't in a group

    .. cpp:member:: OcaTimeMode TimeMode

        Absolute or Relative time.

    .. cpp:member:: OcaONo TimeSourceONo

        ONo of relevant **OcaTimeSource** object or zero to use device time
        (see **OcaDeviceTimeManager** ).

    .. cpp:member:: OcaTimePTP StartTime

        Time at which to start task, or zero if task will be manually started.
        If **TimeMode=Relative** , the actual event start time equals the
        value of **StartTime** plus the absolute time that **StartTime** was
        most recently set. Datatype shall depend on value of **TimeUnits** : -
        If **TimeUnits** is seconds, datatype shall be **OcaTimePTP;** - If
        TimeUnits is samples, datatype shall be **OcaUint64** . If
        **TimeMode=Absolute** , the actual event start time equals the value
        of **StartTime**

    .. cpp:member:: OcaTimePTP Duration

        Duration of task execution, or zero to run until complete or
        explicitly stopped.

    .. cpp:member:: OcaBlob ApplicationSpecificParameters

        Arbitrary application-specific parameters for the Task and its
        Program.


OCP.1 Encoding
--------------

====================================== =========== ===========
Field                                  Basic type  Byte length
====================================== =========== ===========
ID.Value                               OcaUint32   4          
Label.Len                              OcaUint16   2          
Label.Value                            string      variable   
ProgramID.Library.ONo                  OcaUint32   4          
ProgramID.ID.Value                     OcaUint32   4          
GroupID.Value                          OcaUint16   2          
TimeMode                               OcaTimeMode variable   
TimeSourceONo.ONo                      OcaUint32   4          
StartTime                              OcaTimePTP  variable   
Duration                               OcaTimePTP  variable   
ApplicationSpecificParameters.DataSize OcaUint16   2          
ApplicationSpecificParameters.Data     OcaUint8    1 * Count  
====================================== =========== ===========


.. _OcaTaskCommand:

OcaTaskCommand
==============

.. cpp:enum:: OcaTaskCommand : uint8_t

    Commands controllers can send to OcaTasks to change their states

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.
    .. cpp:enumerator:: Prepare = 1

        Initialize task. If successful, resulting task state is **Disabled** .
        In this state, a prescheduled task will not automatically run, nor can
        the task be started with a **Start** command.
    .. cpp:enumerator:: Enable = 2

        Make task available for scheduled or manual start. If successful,
        resulting task state is **Enabled** . In this state, the task can be
        started manually or at a scheduled time.
    .. cpp:enumerator:: Start = 3

        Start task execution immediately. If successful, resulting task state
        is **Running** .
    .. cpp:enumerator:: Stop = 4

        Stop task gracefully. If successful, resulting task state is
        **Stopped** .
    .. cpp:enumerator:: Abort = 5

        Unconditionally terminate task immediately. Resulting task status is
        **Aborted** .
    .. cpp:enumerator:: Disable = 6

        Place task into **Disabled** state. In this state, a prescheduled task
        will not automatically run, nor can the task be started with a
        **Start** command.
    .. cpp:enumerator:: Clear = 7

        De-initialize task. Place it into the **NotPrepared** state.
.. _OcaTaskManagerState:

OcaTaskManagerState
===================

.. cpp:enum:: OcaTaskManagerState : uint8_t

    States of **OcaTaskManager** object. These states represent the
    overall state of task processing in the device.
    
    - Device task processing state is **Enabled** by default. In
    **Enabled** state, tasks may be running.
    
    
    - Device task processing state may be **Disabled** by the
    **OcaTaskManager Disable** command.
    
    
    - The **Disable** command will succeed only if no tasks are running.
    Tasks may be stopped by:
    
    - passing the **OcaTaskManager** a **Stop** or **Abort** command,
    which will stop all tasks in the device; or
    
    
    - passing a **Stop** or **Abort** command to each **OcaTaskGroup**
    agent, which will stop all the tasks in the given task groups; or
    
    
    - passing a **Stop** or **Abort** command to each task individually.
    

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.
    .. cpp:enumerator:: Enabled = 1

        Task processing is enabled. Tasks may be running.
    .. cpp:enumerator:: Disabled = 2

        Task processing is disabled. No tasks are running.
.. _OcaRamperInterpolationLaw:

OcaRamperInterpolationLaw
=========================

.. cpp:enum:: OcaRamperInterpolationLaw : uint8_t

    Interpolation law for ramper to use.

    .. cpp:enumerator:: Linear = 1

        Linear interpolation law
    .. cpp:enumerator:: ReverseLinear = 2

        Reverse linear interpolation law
    .. cpp:enumerator:: Sine = 3

        Sine interpolation law
    .. cpp:enumerator:: Exponential = 4

        Exponential interpolation law