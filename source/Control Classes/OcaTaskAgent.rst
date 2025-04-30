.. _ocataskagent:

1.2.12  OcaTaskAgent
====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaTaskAgent <ocataskagent>`

.. cpp:class:: OcaTaskAgent: OcaAgent

    Task scheduler. Holds a queue of task-program pairs to be executed under
    specific future conditions.

    **Properties**:


    .. _ocataskagent_blocked:

    .. cpp:member:: OcaBoolean Blocked

        If value is TRUE, the task agent is allowed to complete any work in
        progress, but is prevented from accepting any new work. When TRUE, the
        methods **ActionPrepare, ActionRun,** and **ActionStart** will fail with
        **OcaStatus = ProcessingFailed**.

        This property has id ``3.5``.

    .. _ocataskagent_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.12"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocataskagent_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocataskagent_executableono:

    .. cpp:member:: OcaONo ExecutableONo

        **ONo** of **OcaProgram** or **OcaCommandSet** assigned to this task.
        Set by the **ActionPrepare(...)** and **ActionRun(...)** methods. Value
        is zero if no **OcaProgram** or **OcaCommandSet** is attached. or zero
        if no executable is assigned.

        This property has id ``3.1``.

    .. _ocataskagent_executionparameters:

    .. cpp:member:: OcaBlob ExecutionParameters

        Application-specific parameters for running the executable, as set by
        the methods **ActionPrepare(...)** and **ActionRun(...)**. Value is an
        empty blob if**** if no execution is pending. or in progress.

        This property has id ``3.3``.

    .. _ocataskagent_groupid:

    .. cpp:member:: OcaID16 GroupID

        ID of group the task is in, or zero if it isn't in a group

        This property has id ``3.2``.

    .. _ocataskagent_operationalstate:

    .. cpp:member:: OcaTaskOperationalState OperationalState

        Operational state of this agent's task = {generic state, task-specific
        blob} .

        This property has id ``3.6``.

    .. _ocataskagent_runmode:

    .. cpp:member:: OcaProgramRunMode RunMode

        Run mode as set by the methods **ActionPrepare(...)** and
        **ActionRun(...)**. Value is **None** if no execution is pending or in
        progress.

        This property has id ``3.4``.

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


    .. _ocataskagent_actionprepare:

    .. cpp:function:: OcaStatus ActionPrepare(OcaONo Program, OcaBlob ExecutionParameters, OcaProgramRunMode RunMode)

        Prepares task for program execution, but does not start execution. Sets
        **ExecutableONo** and **ExecutionParameters**. Changes state from
        **NotPrepared** to **Ready**. If property **.Blocked** is TRUE, does
        nothing and returns status of **ProcessingFailed**.

        This method has id ``3.1``.

        - :cpp:expr:`Program`: Input parameter.


        - :cpp:expr:`ExecutionParameters`: Input parameter.


        - :cpp:expr:`RunMode`: Input parameter.


    .. _ocataskagent_actionrun:

    .. cpp:function:: OcaStatus ActionRun(OcaONo Program, OcaBlob ExecutionParameters, OcaProgramRunMode RunMode)

        Execute the given program immediately. Sets **ExecutableONo** and
        **ExecutionParameters**. Changes state from **NotPrepared** to
        **Running**. If property **.Blocked** is TRUE, does nothing and returns
        status of **ProcessingFailed**.

        This method has id ``3.2``.

        - :cpp:expr:`Program`: Input parameter.


        - :cpp:expr:`ExecutionParameters`: Input parameter.


        - :cpp:expr:`RunMode`: Input parameter.


    .. _ocataskagent_actionstart:

    .. cpp:function:: OcaStatus ActionStart()

        Executes the prepared program. Changes state from **Ready** to
        **Running**. If property **.Blocked** is TRUE, does nothing and returns
        status of **ProcessingFailed**.

        This method has id ``3.3``.

    .. _ocataskagent_actionstop:

    .. cpp:function:: OcaStatus ActionStop()

        Requests orderly termination of running program. Changes state from
        **Running** to **Stopping**. When termination is complete, state changes
        from **Stopping** to **Ended.**

        This method has id ``3.4``.

    .. _ocataskagent_actionreset:

    .. cpp:function:: OcaStatus ActionReset()

        Resets all internal states to their values at start of execution. Forces
        immediate termination of running or stopping program. Changes state from
        **Running, Stopping,** or **Ended** to **Ready.**

        This method has id ``3.5``.

    .. _ocataskagent_actionclear:

    .. cpp:function:: OcaStatus ActionClear()

        Clears all memory of program and program execution from the task agent.
        Forces immediate termination of running or stopping program. Changes
        state from **Running, Stopping,** or **Ended** to **NotPrepared. ** Sets
        property **ExecutableONo** to zero, property **ExecutionParameters** to
        a null blob, and property **RunMode** to **None**.

        This method has id ``3.6``.

    .. _ocataskagent_getblocked:

    .. cpp:function:: OcaStatus GetBlocked(OcaBoolean &Blocked)

        Gets property **Blocked**.

        This method has id ``3.7``.

        - :cpp:expr:`Blocked`: Output parameter.


    .. _ocataskagent_setblocked:

    .. cpp:function:: OcaStatus SetBlocked(OcaBoolean Blocked)

        Sets the **Blocked** property.

        This method has id ``3.8``.

        - :cpp:expr:`Blocked`: Input parameter.


    .. _ocataskagent_getoperationalstate:

    .. cpp:function:: OcaStatus GetOperationalState(OcaTaskOperationalState &State)

        Gets value of the **OperationalState** property.

        This method has id ``3.9``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocataskagent_getexecutableono:

    .. cpp:function:: OcaStatus GetExecutableONo(OcaONo &ONo)

        Gets value of **ExecutableONo** property, as set by the
        **ActionPrepare(...)** and **ActionRun(...)** methods. Returns zero if
        no execution is pending or in progress.

        This method has id ``3.10``.

        - :cpp:expr:`ONo`: Output parameter.


    .. _ocataskagent_getexecutionparameters:

    .. cpp:function:: OcaStatus GetExecutionParameters(OcaBlob &Parameters)

        Gets value of **ExecutionParameters** property, as set by the
        **ActionPrepare(...)** and **ActionRun(...)** methods. Returns an empty
        blob if no execution is pending or in progress.

        This method has id ``3.11``.

        - :cpp:expr:`Parameters`: Output parameter.


    .. _ocataskagent_getrunmode:

    .. cpp:function:: OcaStatus GetRunMode(OcaProgramRunMode &RunMode)

        Gets the value of the **RunMode** property, as set by the
        **ActionPrepare(...)** and **ActionRun(...)** methods. Returns the value
        **None** if no execution is pending or in progress.

        This method has id ``3.12``.

        - :cpp:expr:`RunMode`: Output parameter.


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


    **Events**:


    .. _ocataskagent_executionterminated:

    .. cpp:function:: void ExecutionTerminated(OcaTaskExecutionTerminatedEventData EventData)

        Event raised when execution terminates for any reason.

        This event has id ``3.1``.
