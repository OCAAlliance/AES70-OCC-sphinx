****************
Ramper Datatypes
****************

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

.. _OcaRamperCommand:

OcaRamperCommand
================

.. cpp:enum:: OcaRamperCommand : uint8_t

    Command repertoire of OcaRamper's **Control** method.

    .. cpp:enumerator:: Enable = 1

        Enable the ramper. Enter **Enabled** state.

    .. cpp:enumerator:: Start = 2

        Unconditionally start ramping now. Enter **Ramping** state.

    .. cpp:enumerator:: Halt = 3

        If **Ramping**, stop ramping. Return to **Initialized** or **Scheduled**
        state, whichever is appropriate.

.. _OcaRamperState:

OcaRamperState
==============

.. cpp:enum:: OcaRamperState : uint8_t

    States of the Ramper . Here are the rules for Ramper state changes:

     - A freshly-constructed Ramper's state shall be **NotInitialized**.

     - A Ramper's state shall become **Initialized** when: Its state is
       **NotInitialized,** AND ** TargetProperty** has been set to a valid
       value, AND ** Goal** has been set, AND ** Duration** has been set.

     - A Ramper's state shall become **Scheduled** when: It is **Initialized,**
       AND **StartWhen** has been set, AND The given start time + **Duration**
       is in the future.

     - A Ramper's state shall become **Enabled** when: Its state is
       **Scheduled,** AND It receives an **Enable **command.

     - A Ramper's state shall become **Ramping** when: It is **Enabled** and the
       ramp start time is reached, OR It is **Initialized**, **Scheduled**, or
       **Enabled** and a **Start** command is received.

     - When a ramp operation completes, or when **Halt** command is received: -
       The Ramper's state shall become **Scheduled**, when: **StartWhen** has
       been set, AND The given start time + **Duration** is in the future. -
       Otherwise, the Ramper's state shall become **Initialized.**



    .. cpp:enumerator:: NotInitialized = 1

        Ramper is not initialized and can not be started or enabled.

    .. cpp:enumerator:: Initialized = 2

        Ramper is initialized sufficiently for nonscheduled ramps to work. A
        nonscheduled ramp is one that has no defined start time and must be
        started with the *Start* command.

    .. cpp:enumerator:: Scheduled = 3

        Ramper is initialized sufficiently for both nonscheduled and scheduled
        ramps to work. A scheduled ramp is one that has a defined start time.

    .. cpp:enumerator:: Enabled = 4

        Ramper's timer is running and scheduled ramp will commence at the
        designated future time.

    .. cpp:enumerator:: Ramping = 5

        Ramper is currently executing a ramp.

