.. _ocataskmanager:

1.3.11  OcaTaskManager
======================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaTaskManager: OcaManager

    Optional manager that collects OcaTask and OcaProgram objects.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 11.
    Tasks shall be device execution threads that start, execute, and
    (normally) stop. The action of an **OcaTask** is defined by an
    **OcaProgram** . The idea is that **OcaTasks** shall execute
    **OcaPrograms** . **OcaTaskManager** offers global control over tasks
    in the device.
    
    - Device task processing state is **Enabled** by default. In
    **Enabled** state, tasks may be running.
    
    
    - Device task processing state may be **Disabled** by the
    **OcaTaskManager Disable** command.
    
    
    - The **Disable** command will succeed only if no tasks are running.
    Tasks may be stopped by: passing the **OcaTaskManager** a **Stop** or
    **Abort** command, which will stop designated tasks in the device;.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaTaskManagerState State

        This property has id ``3.0``.

        Current state of task processing. State is Disabled after a Disable
        command has been received, Enabled otherwise.

    .. cpp:member:: OcaMap<OcaTaskID, OcaTask> Tasks

        This property has id ``3.0``.

        Task collection

    .. cpp:function:: OcaStatus Enable(OcaBoolean Enable)

        This method has id ``3.1``.

        Enables (parameter =TRUE) or disables (parameter = FALSE) the running
        of tasks. Changes value of property State from Disabled to Enabled and
        vice versa. All tasks running when Enable is called with parameter =
        FALSE are immediately aborted.

        :param OcaBoolean Enable: Input parameter.

    .. cpp:function:: OcaStatus ControlAllTasks(OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        This method has id ``3.2``.

        Controls all tasks in device. Return value indicates whether tasks
        were successfully controlled.

        :param OcaTaskCommand Command: Input parameter.
        :param OcaBlob ApplicationTaskParameter: Input parameter.

    .. cpp:function:: OcaStatus ControlTaskGroup(OcaTaskGroupID GroupID, OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        This method has id ``3.3``.

        Controls all tasks in the given group. Return value indicates whether
        tasks were successfully controlled.

        :param OcaTaskGroupID GroupID: Input parameter.
        :param OcaTaskCommand Command: Input parameter.
        :param OcaBlob ApplicationTaskParameter: Input parameter.

    .. cpp:function:: OcaStatus ControlTask(OcaTaskID TaskID, OcaTaskCommand Command, OcaBlob ApplicationTaskParameter)

        This method has id ``3.4``.

        Controls a specified task. Return value indicates whether tasks were
        successfully controlled.

        :param OcaTaskID TaskID: Input parameter.
        :param OcaTaskCommand Command: Input parameter.
        :param OcaBlob ApplicationTaskParameter: Input parameter.

    .. cpp:function:: OcaStatus GetState(OcaTaskManagerState &State)

        This method has id ``3.5``.

        Gets value of property **State** . Return value indicates whether
        value was successfully retrieved.

        :param OcaTaskManagerState State: Output parameter.

    .. cpp:function:: OcaStatus GetTaskStatuses(OcaTaskStatus &Statuses)

        This method has id ``3.6``.


        :param OcaTaskStatus Statuses: Output parameter.

    .. cpp:function:: OcaStatus GetTaskStatus(OcaTaskID TaskID, OcaTaskStatus &Status)

        This method has id ``3.7``.


        :param OcaTaskID TaskID: Input parameter.
        :param OcaTaskStatus Status: Output parameter.

    .. cpp:function:: OcaStatus AddTask(OcaTask Task, OcaTask &Task_)

        This method has id ``3.8``.

        Creates a Task. Parameters of the new Task are given in the Task
        parameter; device returns the same parameter with the new Task ID
        filled in. Initial task state is set to Disabled. Return value
        indicates whether Task was successfully created.

        :param OcaTask Task: Input parameter.
        :param OcaTask Task_: Output parameter.

    .. cpp:function:: OcaStatus GetTasks(OcaMap<OcaTaskID, OcaTask> &Tasks)

        This method has id ``3.9``.

        Gets map of Tasks in the device. Return value indicates whether map
        was successfully retrieved.

        :param OcaMap<OcaTaskID, OcaTask> Tasks: Output parameter.

    .. cpp:function:: OcaStatus GetTask(OcaTaskID ID, OcaTask &Task)

        This method has id ``3.10``.

        Retrieves a Task. Return value indicates whether Task was successfully
        retrieved.

        :param OcaTaskID ID: Input parameter.
        :param OcaTask Task: Output parameter.

    .. cpp:function:: OcaStatus SetTask(OcaTaskID ID, OcaTask Task)

        This method has id ``3.11``.

        Updates a Task. Return value indicates whether Task was successfully
        updated.

        :param OcaTaskID ID: Input parameter.
        :param OcaTask Task: Input parameter.

    .. cpp:function:: OcaStatus DeleteTask(OcaTaskID ID)

        This method has id ``3.12``.

        Deletes a task. Return value indicates whether task was successfully
        deleted. Method fails with status=ProcessingFailed if task is running.

        :param OcaTaskID ID: Input parameter.

