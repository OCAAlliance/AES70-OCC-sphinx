************************
Task Scheduler Datatypes
************************

.. _OcaTaskSchedulerState:

OcaTaskSchedulerState
=====================

.. cpp:enum:: OcaTaskSchedulerState : uint8_t

    States of **OcaTaskScheduler** object. State values shall change when the
    object receives a Command or when processing events (e.g. completion) occur.

    .. cpp:enumerator:: Unknown = 0

        Scheduler is in an unknown state.

    .. cpp:enumerator:: Running = 1

        Scheduler is running normally. All functions are enabled.

    .. cpp:enumerator:: Paused = 2

        Scheduler is paused: no runs will be started, but controller may still
        manage run queues normally.

    .. cpp:enumerator:: Draining = 3

        Enqueued runs are being started normally, but no new run queue items may
        be added. Controllers may still delete run queue items.

    .. cpp:enumerator:: Stopped = 4

        No runs are being scheduled and no run queue maintenance is allowed.

.. _OcaJobQueueItem:

OcaJobQueueItem
===============

.. cpp:struct:: OcaJobQueueItem

    An item of the Job Queue in **OcaTaskAgentManager**.

    .. cpp:member:: OcaID32 ID

        ID of this queue item.

    .. cpp:member:: OcaONo ProgramONo

        ONo of Executable to run

    .. cpp:member:: OcaProgramRunMode RunMode

        Run mode

    .. cpp:member:: OcaBlob RunParameters

        Run parameters to use

    .. cpp:member:: OcaWhen RunWhen

        When to run the Task

    .. cpp:member:: OcaONo RunWhere

        Where to run the Task. Special values are as follows: 0 do not run 1 run
        on any available task in the scheduler's task list 2-4095 reserved
        4096-up Value of ONo of OcaTaskAgent to use

