.. _ocataskmanager:

1.3.11  OcaTaskManager
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaTaskManager <ocataskmanager>`

.. cpp:class:: OcaTaskManager: OcaManager

    This class is **deprecated** in version 2 (OCA 1.5). Optional manager that
    collects **OcaTask** and **OcaProgram** objects.

     - May be instantiated once in any device.

     - If instantiated, object number must be 11.


    Tasks shall be device execution threads that start, execute, and (normally)
    stop. The action of an **OcaTask** is defined by an **OcaProgram**. The idea
    is that **OcaTasks** shall execute **OcaPrograms**. **OcaTaskManager**
    offers global control over tasks in the device.

     - Device task processing state is **Enabled** by default. In **Enabled**
       state, tasks may be running.

     - Device task processing state may be **Disabled** by the **OcaTaskManager
       Disable** command.

     - The **Disable** command will succeed only if no tasks are running.


    Tasks may be stopped by: passing the **OcaTaskManager** a **Stop** or
    **Abort** command, which will stop designated tasks in the device;.

    **Properties**:


    .. _ocataskmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.11"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocataskmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocataskmanager_state:

    .. cpp:member:: OcaTaskManagerState State

        Current state of task processing. State is Disabled after a Disable
        command has been received, Enabled otherwise.

        This property has id ``3.1``.

    .. _ocataskmanager_tasks:

    .. cpp:member:: OcaMap<OcaTaskID, OcaTask> Tasks

        Task collection

        This property has id ``3.2``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocataskmanager_enable:

    .. cpp:function:: OcaStatus Enable(OcaBoolean Enable)

        Enables (parameter =TRUE) or disables (parameter = FALSE) the running of
        tasks. Changes value of property State from Disabled to Enabled and vice
        versa. All tasks running when Enable is called with parameter = FALSE
        are immediately aborted.

        This method has id ``3.1``.

        - :cpp:expr:`Enable`: Input parameter.


    .. _ocataskmanager_controlalltasks:

    .. cpp:function:: OcaStatus ControlAllTasks(OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        Controls all tasks in device. Return value indicates whether tasks were
        successfully controlled.

        This method has id ``3.2``.

        - :cpp:expr:`Command`: Input parameter.


        - :cpp:expr:`ApplicationTaskParameter`: Input parameter.


    .. _ocataskmanager_controltaskgroup:

    .. cpp:function:: OcaStatus ControlTaskGroup(OcaID16 GroupID, OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        Controls all tasks in the given group. Return value indicates whether
        tasks were successfully controlled.

        This method has id ``3.3``.

        - :cpp:expr:`GroupID`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


        - :cpp:expr:`ApplicationTaskParameter`: Input parameter.


    .. _ocataskmanager_controltask:

    .. cpp:function:: OcaStatus ControlTask(OcaTaskID TaskID, OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        Controls a specified task. Return value indicates whether tasks were
        successfully controlled.

        This method has id ``3.4``.

        - :cpp:expr:`TaskID`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


        - :cpp:expr:`ApplicationTaskParameter`: Input parameter.


    .. _ocataskmanager_getstate:

    .. cpp:function:: OcaStatus GetState(OcaTaskManagerState &State)

        Gets value of property **State**. Return value indicates whether value
        was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocataskmanager_gettaskstatuses:

    .. cpp:function:: OcaStatus GetTaskStatuses(OcaTaskStatus &Statuses)


        This method has id ``3.6``.

        - :cpp:expr:`Statuses`: Output parameter.


    .. _ocataskmanager_gettaskstatus:

    .. cpp:function:: OcaStatus GetTaskStatus(OcaTaskID TaskID, OcaTaskStatus &Status)


        This method has id ``3.7``.

        - :cpp:expr:`TaskID`: Input parameter.


        - :cpp:expr:`Status`: Output parameter.


    .. _ocataskmanager_addtask:

    .. cpp:function:: OcaStatus AddTask()

        Creates a Task. Parameters of the new Task are given in the Task
        parameter; device returns the same parameter with the new Task ID filled
        in. Initial task state is set to Disabled. Return value indicates
        whether Task was successfully created.

        This method has id ``3.8``.

    .. _ocataskmanager_gettasks:

    .. cpp:function:: OcaStatus GetTasks(OcaMap<OcaTaskID, OcaTask> &Tasks)

        Gets map of Tasks in the device. Return value indicates whether map was
        successfully retrieved.

        This method has id ``3.9``.

        - :cpp:expr:`Tasks`: Output parameter.


    .. _ocataskmanager_gettask:

    .. cpp:function:: OcaStatus GetTask(OcaTaskID ID, OcaTask &Task)

        Retrieves a Task. Return value indicates whether Task was successfully
        retrieved.

        This method has id ``3.10``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Task`: Output parameter.


    .. _ocataskmanager_settask:

    .. cpp:function:: OcaStatus SetTask(OcaTaskID ID, OcaTask Task)

        Updates a Task. Return value indicates whether Task was successfully
        updated.

        This method has id ``3.11``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Task`: Input parameter.


    .. _ocataskmanager_deletetask:

    .. cpp:function:: OcaStatus DeleteTask(OcaTaskID ID)

        Deletes a task. Return value indicates whether task was successfully
        deleted. Method fails with status=ProcessingFailed if task is running.

        This method has id ``3.12``.

        - :cpp:expr:`ID`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`


    **Events**:


    .. _ocataskmanager_taskstatechanged:

    .. cpp:function:: void TaskStateChanged(OcaTaskStatusChangedEventData EventData)


        This event has id ``3.1``.
