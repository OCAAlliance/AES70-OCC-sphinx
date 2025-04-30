.. _ocataskscheduler:

1.2.13  OcaTaskScheduler
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaTaskScheduler <ocataskscheduler>`

.. cpp:class:: OcaTaskScheduler: OcaAgent

    Optional scheduler for scheduling tasks to run programs and commandsets in
    the future.

    **Properties**:


    .. _ocataskscheduler_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocataskscheduler_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocataskscheduler_jobqueue:

    .. cpp:member:: OcaList<OcaJobQueueItem> JobQueue

        List of queued jobs. Items are added to the queue by the **AddJob()**
        method, and removed from the queue when they have run to completion, or
        by the **DeleteJob()** or **ClearJobQueue()** methods.

        This property has id ``3.3``.

    .. _ocataskscheduler_state:

    .. cpp:member:: OcaTaskSchedulerState State

        See **OcaTaskSchedulerState** for state values and their semantics.

        This property has id ``3.1``.

    .. _ocataskscheduler_taskagents:

    .. cpp:member:: OcaList<OcaONo> TaskAgents

        List of ONos of **OcaTaskAgent** objects. Readonly; updated
        automatically when **OcaTaskAgent** objects are created or deleted.

        This property has id ``3.2``.

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


    .. _ocataskscheduler_actionstart:

    .. cpp:function:: OcaStatus ActionStart()

        Changes state to **Running.**

        This method has id ``3.1``.

    .. _ocataskscheduler_actionstop:

    .. cpp:function:: OcaStatus ActionStop()

        Changes state to **Stopped.**

        This method has id ``3.2``.

    .. _ocataskscheduler_actionpause:

    .. cpp:function:: OcaStatus ActionPause()

        Changes state to **Paused.**

        This method has id ``3.3``.

    .. _ocataskscheduler_actiondrain:

    .. cpp:function:: OcaStatus ActionDrain()

        Changes state to **Draining.**

        This method has id ``3.4``.

    .. _ocataskscheduler_getstate:

    .. cpp:function:: OcaStatus GetState(OcaTaskSchedulerState &State)

        Gets the scheduler's state.

        This method has id ``3.5``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocataskscheduler_gettaskagents:

    .. cpp:function:: OcaStatus GetTaskAgents(OcaList<OcaONo> &ONos)

        Gets the list of all **OcaTaskAgent** ONos.

        This method has id ``3.6``.

        - :cpp:expr:`ONos`: Output parameter.


    .. _ocataskscheduler_getjobqueue:

    .. cpp:function:: OcaStatus GetJobQueue(OcaList<OcaJobQueueItem> &Queue)

        Gets the job queue.

        This method has id ``3.7``.

        - :cpp:expr:`Queue`: Output parameter.


    .. _ocataskscheduler_getjob:

    .. cpp:function:: OcaStatus GetJob(OcaID32 ID, OcaJobQueueItem &Item)

        Gets a jobqueue item, given its ID.

        This method has id ``3.8``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Item`: Output parameter.


    .. _ocataskscheduler_setjob:

    .. cpp:function:: OcaStatus SetJob(OcaID32 ID, OcaJobQueueItem Item)

        Replaces a job queue item, given its ID. If given ID references a
        nonexistent job queue item, method shall return status value
        **ParameterOutOfRange**.

        This method has id ``3.9``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Item`: Input parameter.


    .. _ocataskscheduler_addjob:

    .. cpp:function:: OcaStatus AddJob(OcaJobQueueItem Item, OcaID32 &ID)

        Adds a job queue item, returns its ID.

        This method has id ``3.10``.

        - :cpp:expr:`Item`: Input parameter.


        - :cpp:expr:`ID`: Output parameter.


    .. _ocataskscheduler_deletejob:

    .. cpp:function:: OcaStatus DeleteJob(OcaID32 ID)

        Deletes a job queue item given its ID.

        This method has id ``3.11``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocataskscheduler_clearjobqueue:

    .. cpp:function:: OcaStatus ClearJobQueue()

        Deletes all job queue items.

        This method has id ``3.12``.

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


    .. _ocataskscheduler_jobdisposed:

    .. cpp:function:: void JobDisposed(OcaJobDisposedEventData EventData)

        Event raised when a job queue item is removed from the queue, either
        because it has fulfilled its purpose or because it has been explicitly
        deleted by the **DeleteJob()** or **ClearJobQueue()** method.

        This event has id ``3.1``.
