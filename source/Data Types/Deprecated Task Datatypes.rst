*************************
Deprecated Task Datatypes
*************************

.. _OcaTaskID:

OcaTaskID
=========

.. cpp:type:: OcaTaskID = OcaUint32

    ID of a Task (i.e. ID of an instance of the OcaTask datatype).
    **Deprecated** in OCA 1.5.

.. _OcaTaskStatus:

OcaTaskStatus
=============

.. cpp:struct:: OcaTaskStatus

    Status of an OcaTask: task state plus an error code that gives more detail.
    **Deprecated** in OCA 1.5.

    .. cpp:member:: OcaTaskID ID

        ID of the task to which this state descriptor applies.

    .. cpp:member:: OcaTaskState State

        State of the task - running, stopped, etc.

    .. cpp:member:: OcaUint16 ErrorCode

        Error code. Value is application-specific.

.. _OcaTaskState:

OcaTaskState
============

.. cpp:enum:: OcaTaskState : uint8_t

    States of OcaTask object. State values change as a result of the object's
    having received a comment or encountering processing events (e.g.
    completion).

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

    An execution thread that runs an AES70 Program. Programs are OcaLibrary
    volumes that contain application-specific execution instructions. **
    Deprecated** in OCA 1.5.

    .. cpp:member:: OcaTaskID ID

        Task ID - assigned by OcaTaskManager

    .. cpp:member:: OcaString Label


    .. cpp:member:: OcaLibVolIdentifier ProgramID

        ID of program this task was given or all null if it's idle.

    .. cpp:member:: OcaID16 GroupID

        ID of group the task is in, or zero if it isn't in a group

    .. cpp:member:: OcaTimeMode TimeMode

        Absolute or Relative time.

    .. cpp:member:: OcaONo TimeSourceONo

        ONo of relevant OcaTimeSource object, or zero if none.

    .. cpp:member:: OcaTime StartTime

        Time at which to start task, or zero if task will be manually started.
        If **TimeMode=Relative**, the actual event start time equals the value
        of **StartTime** plus the absolute time that **StartTime** was most
        recently set. Datatype shall depend on value of **TimeUnits**: - If
        **TimeUnits** is seconds, datatype shall be **OcaTime;** - If TimeUnits
        is samples, datatype shall be **OcaUint64**. If **TimeMode=Absolute**,
        the actual event start time equals the value of **StartTime**

    .. cpp:member:: OcaTimeInterval Duration

        Duration of task execution, or zero to run until complete or explicitly
        stopped.

    .. cpp:member:: OcaBlob ApplicationSpecificParameters

        Arbitrary application-specific parameters for the Task and its Program.

.. _OcaTaskCommand:

OcaTaskCommand
==============

.. cpp:enum:: OcaTaskCommand : uint8_t

    Commands controllers can send to OcaTasks to change their states.
    **Deprecated** in OCA 1.5.

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.

    .. cpp:enumerator:: Prepare = 1

        Initialize task. If successful, resulting task state is **Ready**, but
        the task is not running.

    .. cpp:enumerator:: Start = 3

        Start task execution. Initial state must be **Ready**. If successful,
        resulting task state is **Running**. If unsuccessful, resulting state is
        **Ended**, with an externally stored result code indicating failed
        start. See **OcaTaskExecutionResult** for standard result codes.

    .. cpp:enumerator:: Stop = 4

        Stop task gracefully. If successful, resulting task state is **Ended. **
        If unsuccessful, resulting task state is unchanged.

    .. cpp:enumerator:: Abort = 5

        Unconditionally terminate task immediately. Resulting task status is
        **Aborted**.

    .. cpp:enumerator:: Disable = 6

        Place task into **Disabled** state. In this state, a prescheduled task
        will not automatically run, nor can the task be started with a **Start**
        command.

    .. cpp:enumerator:: Clear = 7

        De-initialize task. Place it into the **NotPrepared** state.

.. _OcaTaskManagerState:

OcaTaskManagerState
===================

.. cpp:enum:: OcaTaskManagerState : uint8_t

    States of **OcaTaskManager** object. These states represent the overall
    state of task processing in the device.

     - Device task processing state is **Enabled** by default. In **Enabled**
       state, tasks may be running.

     - Device task processing state may be **Disabled** by the **OcaTaskManager
       Disable** command.

     - The **Disable** command will succeed only if no tasks are running.


    Tasks may be stopped by:

     - passing the **OcaTaskManager** a **Stop** or **Abort** command, which
       will stop all tasks in the device; or

     - passing a **Stop** or **Abort** command to each **OcaTaskGroup** agent,
       which will stop all the tasks in the given task groups; or

     - passing a **Stop** or **Abort** command to each task individually.


    **Deprecated** in OCA 1.5.

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.

    .. cpp:enumerator:: Enabled = 1

        Task processing is enabled. Tasks may be running.

    .. cpp:enumerator:: Disabled = 2

        Task processing is disabled. No tasks are running.

.. _OcaTaskStatusChangedEventData:

OcaTaskStatusChangedEventData
=============================

.. cpp:struct:: OcaTaskStatusChangedEventData

    **Deprecated** event raised by **OcaTaskManager** when the status of a
    legacy task changes. Legacy task are task that execute now-deprecated
    **OcaLibrary** volumes.

    .. cpp:member:: OcaTaskID TaskID

        ID of Task

    .. cpp:member:: OcaLibVolIdentifier ProgramID

        Identifier of OcaLibrary volume that was executing.

    .. cpp:member:: OcaTaskStatus Status

        New task status

.. _OcaTaskStatusChangedEventData2:

OcaTaskStatusChangedEventData2
==============================

.. cpp:struct:: OcaTaskStatusChangedEventData2

    Notification data returned by the **OcaTaskManager2.TaskStatusChanged()**
    event. Deprecated in OCA 1.5.

    .. cpp:member:: OcaTaskID TaskID

        ID of Task

    .. cpp:member:: OcaONo ProgramONo

        Object number of program **OcaDataset** the task is running.

    .. cpp:member:: OcaTaskStatus Status

        New task status

