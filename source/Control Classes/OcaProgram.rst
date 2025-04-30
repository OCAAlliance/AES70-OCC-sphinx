.. _ocaprogram:

1.5.2  OcaProgram
=================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaDataset <ocadataset>` : :ref:`OcaProgram <ocaprogram>`

.. cpp:class:: OcaProgram: OcaDataset

    A Program. Child of **OcaDataset**. **Execution:** A program executes in a
    task. Tasks may be explicitly created by **OcaTaskManager2**, or they may be
    implicitly created at execution time. The execution task may be explicitly
    specified, by giving its task ID, or automatically created by the device. In
    either case, the given task ID parameter will be updated by the **Run()** or
    **Schedule()** method call to reflect the task actually assigned to the run.
    Once a task is set up, subscribing controllers will receive notifications
    about changes in its status from **OcaTaskManager2.** As well, running tasks
    can be controlled using **OcaTaskManager2** methods. Running and scheduling
    methods are as follows:

     - **Run(...)** starts execution, then returns immediately.

     - **Schedule(...)** schedules execution, then returns immediately.

     - **RunWait(...)** starts execution, but does not return until execution
       terminates.

     - **ScheduleWait(...)** schedules execution, but does not return until
       execution termiantes.


    If execution is invoked via **Run(...)** or **Schedule(...),
    OcaTaskManager2** will raise a **CommandSetTerminated** event when execution
    terminates. If execution is invoked via **RunWait(...)** or
    **ScheduleWait(...),** termination information is returned by the method,
    and no such event is raised.

    **Properties**:


    .. _ocaprogram_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.5.2"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

        This property has id ``1.1``.

    .. _ocaprogram_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaprogram_supportedrunmodes:

    .. cpp:member:: OcaList<OcaProgramRunMode> SupportedRunModes

        List of runmodes the task supports.

        This property has id ``3.1``.

    Properties inherited from :ref:`ocadataset`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaDataset::ClassID <ocadataset_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaDataset::ClassVersion <ocadataset_classversion>`

    - :cpp:texpr:`OcaTime` :ref:`OcaDataset::LastModificationTime <ocadataset_lastmodificationtime>`

    - :cpp:texpr:`OcaUint64` :ref:`OcaDataset::MaxSize <ocadataset_maxsize>`

    - :cpp:texpr:`OcaString` :ref:`OcaDataset::Name <ocadataset_name>`

    - :cpp:texpr:`OcaONo` :ref:`OcaDataset::Owner <ocadataset_owner>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaDataset::ReadOnly <ocadataset_readonly>`

    - :cpp:texpr:`OcaMimeType` :ref:`OcaDataset::Type <ocadataset_type>`


    **Methods**:


    .. _ocaprogram_getsupportedrunmodes:

    .. cpp:function:: OcaStatus GetSupportedRunModes(OcaList<OcaProgramRunMode> &RunModes)

        Gets the list of run modes this program supports.

        This method has id ``3.1``.

        - :cpp:expr:`RunModes`: Output parameter.


    .. _ocaprogram_setsupportedrunmodes:

    .. cpp:function:: OcaStatus SetSupportedRunModes(OcaList<OcaProgramRunMode> RunModes)

        Sets the list of run modes this program supports.

        This method has id ``3.2``.

        - :cpp:expr:`RunModes`: Input parameter.


    Methods inherited from :ref:`ocadataset`:

    - :ref:`OcaDataset::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaDataset::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaDataset::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaDataset::GetRole <ocaroot_getrole>`

    - :ref:`OcaDataset::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaDataset::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaDataset::Unlock <ocaroot_unlock>`

    - :ref:`OcaDataset::Clear <ocadataset_clear>`

    - :ref:`OcaDataset::Close <ocadataset_close>`

    - :ref:`OcaDataset::GetDatasetSizes <ocadataset_getdatasetsizes>`

    - :ref:`OcaDataset::GetLastModificationTime <ocadataset_getlastmodificationtime>`

    - :ref:`OcaDataset::GetName <ocadataset_getname>`

    - :ref:`OcaDataset::GetOwner <ocadataset_getowner>`

    - :ref:`OcaDataset::GetReadOnly <ocadataset_getreadonly>`

    - :ref:`OcaDataset::GetType <ocadataset_gettype>`

    - :ref:`OcaDataset::OpenRead <ocadataset_openread>`

    - :ref:`OcaDataset::OpenWrite <ocadataset_openwrite>`

    - :ref:`OcaDataset::Read <ocadataset_read>`

    - :ref:`OcaDataset::SetName <ocadataset_setname>`

    - :ref:`OcaDataset::SetReadOnly <ocadataset_setreadonly>`

    - :ref:`OcaDataset::SetType <ocadataset_settype>`

    - :ref:`OcaDataset::Write <ocadataset_write>`

