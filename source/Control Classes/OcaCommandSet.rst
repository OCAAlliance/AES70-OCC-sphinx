.. _ocacommandset:

1.5.2.1  OcaCommandSet
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaDataset <ocadataset>` : :ref:`OcaProgram <ocaprogram>` : :ref:`OcaCommandSet <ocacommandset>`

.. cpp:class:: OcaCommandSet: OcaProgram

    A command set. Child of **OcaProgram**.

    **Properties**:


    .. _ocacommandset_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.5.2.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

        This property has id ``1.1``.

    .. _ocacommandset_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocacommandset_commands:

    .. cpp:member:: OcaList<OcaCommand> Commands

        The commands in the commandSet.

        This property has id ``4.1``.

    Properties inherited from :ref:`ocaprogram`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaProgram::ClassID <ocaprogram_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaProgram::ClassVersion <ocaprogram_classversion>`

    - :cpp:texpr:`OcaList<OcaProgramRunMode>` :ref:`OcaProgram::SupportedRunModes <ocaprogram_supportedrunmodes>`


    **Methods**:


    .. _ocacommandset_getcommands:

    .. cpp:function:: OcaStatus GetCommands(OcaList<OcaCommand> &Commands)

        Gets the list of commands in the commandset.

        This method has id ``4.1``.

        - :cpp:expr:`Commands`: Output parameter.


    .. _ocacommandset_setcommands:

    .. cpp:function:: OcaStatus SetCommands(OcaList<OcaCommand> Commands)

        Sets the list of commands in the commandset.

        This method has id ``4.2``.

        - :cpp:expr:`Commands`: Input parameter.


    .. _ocacommandset_getcommand:

    .. cpp:function:: OcaStatus GetCommand(OcaUint16 Index, OcaCommand &Command)

        Gets the command designated by the **Index** parameter.

        This method has id ``4.3``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Command`: Output parameter.


    .. _ocacommandset_setcommand:

    .. cpp:function:: OcaStatus SetCommand(OcaUint16 Index, OcaCommand Command)

        Replaces the command designated by the **Index** parameter.

        This method has id ``4.4``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


    .. _ocacommandset_insertcommand:

    .. cpp:function:: OcaStatus InsertCommand(OcaUint16 Index, OcaCommand Command)

        Inserts a command into the CommandSet after the command with the given
        **Index** value.

        This method has id ``4.5``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


    .. _ocacommandset_deletecommand:

    .. cpp:function:: OcaStatus DeleteCommand(OcaUint16 Index)

        Removes command with the given **Index** value from the commandset.

        This method has id ``4.6``.

        - :cpp:expr:`Index`: Input parameter.


    .. _ocacommandset_clear:

    .. cpp:function:: OcaStatus Clear()

        Removes all commands from the command set.

        This method has id ``4.7``.

    Methods inherited from :ref:`ocaprogram`:

    - :ref:`OcaProgram::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaProgram::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaProgram::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaProgram::GetRole <ocaroot_getrole>`

    - :ref:`OcaProgram::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaProgram::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaProgram::Unlock <ocaroot_unlock>`

    - :ref:`OcaProgram::Clear <ocadataset_clear>`

    - :ref:`OcaProgram::Close <ocadataset_close>`

    - :ref:`OcaProgram::GetDatasetSizes <ocadataset_getdatasetsizes>`

    - :ref:`OcaProgram::GetLastModificationTime <ocadataset_getlastmodificationtime>`

    - :ref:`OcaProgram::GetName <ocadataset_getname>`

    - :ref:`OcaProgram::GetOwner <ocadataset_getowner>`

    - :ref:`OcaProgram::GetReadOnly <ocadataset_getreadonly>`

    - :ref:`OcaProgram::GetType <ocadataset_gettype>`

    - :ref:`OcaProgram::OpenRead <ocadataset_openread>`

    - :ref:`OcaProgram::OpenWrite <ocadataset_openwrite>`

    - :ref:`OcaProgram::Read <ocadataset_read>`

    - :ref:`OcaProgram::SetName <ocadataset_setname>`

    - :ref:`OcaProgram::SetReadOnly <ocadataset_setreadonly>`

    - :ref:`OcaProgram::SetType <ocadataset_settype>`

    - :ref:`OcaProgram::Write <ocadataset_write>`

    - :ref:`OcaProgram::GetSupportedRunModes <ocaprogram_getsupportedrunmodes>`

    - :ref:`OcaProgram::SetSupportedRunModes <ocaprogram_setsupportedrunmodes>`

