********************
Task Agent Datatypes
********************

.. _OcaTaskGenericState:

OcaTaskGenericState
===================

.. cpp:enum:: OcaTaskGenericState : uint8_t

    States of OcaTask object. State values shall change as a result of the
    object's having received a Command or encountering processing events (e.g.
    completion).

    .. cpp:enumerator:: None = 0

        No (invalid) encoding.

    .. cpp:enumerator:: Idle = 1

        Task is ready to be initialized.

    .. cpp:enumerator:: Ready = 2

        Task is initialized.

    .. cpp:enumerator:: Running = 3

        Task is executing.

    .. cpp:enumerator:: Ended = 4

        Execution has terminated. Success or failure is indicated elsewhere.

.. _OcaTaskOperationalState:

OcaTaskOperationalState
=======================

.. cpp:struct:: OcaTaskOperationalState

    Operational state of task: generic state + task-specific details

    .. cpp:member:: OcaTaskGenericState Generic

        Generic state of this Task Agent.

    .. cpp:member:: OcaList<OcaTypedBlob> Details

        Device-specific state details (optional)

.. _OcaGenericEndState:

OcaGenericEndState
==================

.. cpp:enum:: OcaGenericEndState : uint8_t

    Reasons why a Commandset terminated

    .. cpp:enumerator:: CompletedNormally = 1

        Commandset terminated normally

    .. cpp:enumerator:: CompletedAbnormally = 2

        Commandset terminated in an orderly but exceptional manner.

    .. cpp:enumerator:: Interrupted = 3

        Commandset execution was interrupted by controller action and did not
        complete.

    .. cpp:enumerator:: Failed = 4

        Commandset encountered an error and did not complete.

.. _OcaProgramResult:

OcaProgramResult
================

.. cpp:struct:: OcaProgramResult

    Execution result of a Program.

    .. cpp:member:: OcaGenericEndState EndState

        Completed normally, completed abnormally, aborted, or failed

    .. cpp:member:: OcaList<OcaTypedBlob> Data

        Program-specific return info - may be null.

.. _OcaCommandResult:

OcaCommandResult
================

.. cpp:struct:: OcaCommandResult

    Execution result of a Command in a Commandset.

    .. cpp:member:: OcaStatus Status

        Status code returned by command method. **nb** This field replaces the
        previous field **EndState** as of AES70-2024.

    .. cpp:member:: OcaList<OcaLongBlob> Data

        Command-specific return info - may be null. **nb** Datatype changed from
        **OcaBlob** to **OcaList<OcaLongBlob>** in AES70-2024.

.. _OcaCommandSetResult:

OcaCommandSetResult
===================

.. cpp:struct:: OcaCommandSetResult

    Execution result of a Commandset

    .. cpp:member:: OcaGenericEndState EndState

        Completed normally, completed abnormally, aborted, or failed

    .. cpp:member:: OcaList<OcaCommandResult> CommandResults

        One entry per (successfully or unsuccessfully) executed command.
        Unexecuted commands are not in the list.

.. _OcaProgramRunMode:

OcaProgramRunMode
=================

.. cpp:type:: OcaProgramRunMode = OcaBitSet16

    Two-bit bitset that specifies run mode: Bit 1: ExecutionOrder 0 =
    sequential, 1 = arbitrary // execution order of steps Bit 2: RollBackOnError
    0 = no rollback, 1 = rollback Thus, the RunMode value for simple sequential
    execution with no rollback mechanism shall be 0b00.

