********************
Task Event Datatypes
********************

.. _OcaExecutableType:

OcaExecutableType
=================

.. cpp:enum:: OcaExecutableType : uint8_t

    Types of executable - program or commandset

    .. cpp:enumerator:: Undefined = 0

        Executable type is undefined.

    .. cpp:enumerator:: Program = 1

        Executable is a Program.

    .. cpp:enumerator:: Commandset = 2

        Executable is a Commandset.

.. _OcaJobDisposition:

OcaJobDisposition
=================

.. cpp:enum:: OcaJobDisposition : uint8_t

    Types of run queue item disposition

    .. cpp:enumerator:: RunStarted = 1

        Task Scheduler has successfully started the Executable.

    .. cpp:enumerator:: ItemDeleted = 2

        Controller explicitly deleted he queue item using the
        **DeleteRunQueueItem()** or **ClearRunQueue()** method.

    .. cpp:enumerator:: FailedToStart_TaskNotAvailable = 3

        Executable could not start because designated Task was busy or no free
        Task was available.

    .. cpp:enumerator:: FailedToStart_TaskNotCompatible = 4

        Executable could not start because designated Task was incompatible with
        the given Program or Commandset, or the requested RunMode was not
        supported.

    .. cpp:enumerator:: FailedToStart_ResourceUnavailable = 5

        Executable could not start because a required Device resource was
        unavailable.

    .. cpp:enumerator:: FailedToStart_DeviceError = 6

        Executable could not start because of a Device error.

.. _OcaJobDisposedEventData:

OcaJobDisposedEventData
=======================

.. cpp:struct:: OcaJobDisposedEventData

    Notification data emitted by the **OcaTaskScheduler.RunQueueItemDisposed**
    event.

    .. cpp:member:: OcaJobQueueItem QueueItem

        The job queue item that is the subject of this event

    .. cpp:member:: OcaJobDisposition Disposition

        Enum specifying what happened to the queue item.

    .. cpp:member:: OcaBlob DispositionDetails

        Optional disposition details

.. _OcaTaskExecutionTerminatedEventData:

OcaTaskExecutionTerminatedEventData
===================================

.. cpp:struct:: OcaTaskExecutionTerminatedEventData

    Notification data emitted by the **OcaTaskAgent.TaskChanged** event upon
    successful or unsuccessful termination of an Executable the task agent has
    been running.

    .. cpp:member:: OcaExecutableType ExecutableType

        Type of Executable - Program or Commandset.

    .. cpp:member:: OcaONo ExecutableONo

        Object number of Executable.

    .. cpp:member:: OcaVariant<OcaProgramResult, OcaCommandSetResult> Result

        Execution result: {generic status, program-type-specific details}.
        Datatype depends on whether Executable is a Program or a Commandset.

