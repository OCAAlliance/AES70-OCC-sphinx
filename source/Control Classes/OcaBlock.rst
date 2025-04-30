.. _ocablock:

1.1.3  OcaBlock
===============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaBlock <ocablock>`

.. cpp:class:: OcaBlock: OcaWorker

    Collection object for hierarchical structuring of Control Object
    populations. The term **Block **means an instance of **OcaBlock**. A Block
    may contain **Action Objects** and/or **Dataset Objects**, where: An Action
    Object is defined as one of:

     - Worker object;

     - Agent object;

     - Network Interface object;

     - Network Application object.


    A Dataset Object is defined an instance of **OcaDataset** or of a subclass
    of **OcaDataset**. The term **Block Member** (or just **Member **in context)
    means an object contained in a Block - either an Action Object or a Dataset
    Object. The Block that contains an object is termed the object's **Owner**.
    A Block may define a **Signal Flow** that represents internal signal flows
    among its Members. Typically, a Block contains a set of Members that
    together function as a processing unit -- for example, a crossover channel
    or mixer strip.

    **Properties**:


    .. _ocablock_actionobjects:

    .. cpp:member:: OcaList<OcaObjectIdentification> ActionObjects

        List of object identifiers of Action Objects in the block.

        This property has id ``3.2``.

    .. _ocablock_blockfactoryono:

    .. cpp:member:: const OcaONo BlockFactoryONo

        ONo of Block Factory that created this Block, or zero if none.

        This property has id ``3.10``.

    .. _ocablock_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.3"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocablock_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocablock_configurability:

    .. cpp:member:: const OcaBlockConfigurability Configurability

        Configurability of this Block's Action Objects, Signal Paths, and
        Dataset Objects.

        This property has id ``3.8``.

    .. _ocablock_datasetobjects:

    .. cpp:member:: OcaList<OcaObjectIdentification> DatasetObjects

        List of object identifiers of Dataset Objects in the Block.

        This property has id ``3.7``.

    .. _ocablock_globaltype:

    .. cpp:member:: const OcaGlobalTypeIdentifier GlobalType

        Global Blocktype Identifier for Reusable Blocks. **Added in version 2 of
        this class.**

        This property has id ``3.5``.

    .. _ocablock_mostrecentparamdatasetono:

    .. cpp:member:: OcaONo MostRecentParamDatasetONo

        ONo of the paramDataset most recently applied to this Block. A value of
        zero indicates that there is no current paramDataset. Replaces
        **MostRecentParamSetIdentifier**. Added in version 3 (OCA 1.5).

        This property has id ``3.9``.

    .. _ocablock_mostrecentparamsetidentifier:

    .. cpp:member:: OcaLibVolID MostRecentParamSetIdentifier

        Identifier of the ParamSet most recently applied to this block.
        **Deprecated** in v3 of this class (OCA 1.5)** -** controllers should
        use the new **OcaDataset** method of storing ParamSets.

        This property has id ``3.4``.

    .. _ocablock_onomap:

    .. cpp:member:: const OcaMap<OcaProtoONo, OcaONo> ONoMap

        For Blocks constructed by Block Factories - see class
        **OcaBlockFactoryAgent**. Maps the Block Factory's prototype ONos to the
        actual ONos of the constructed Block. Key is prototype ONo, value is
        actual ONo. Empty if block was not constructed by a Block Factory. Added
        in version 2 of this class.

        This property has id ``3.6``.

    .. _ocablock_signalpaths:

    .. cpp:member:: OcaMap<OcaID16, OcaSignalPath> SignalPaths

        Map of Signal Paths in the Block. Key is Block-local signal path ID.

        This property has id ``3.3``.

    .. _ocablock_type:

    .. cpp:member:: const OcaONo Type

        Readonly Blocktype. Deprecated in v3 of this class.

        This property has id ``3.1``.

    Properties inherited from :ref:`ocaworker`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaMap<OcaPortID, OcaPortClockMapEntry>` :ref:`OcaWorker::PortClockMap <ocaworker_portclockmap>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`


    **Methods**:


    .. _ocablock_gettype:

    .. cpp:function:: OcaStatus GetType(OcaONo &Type)

        Gets the Block type. For statically-defined Blocks, the Block type shall
        be a Uint32 with a value corresponding to the unique configuration of
        this Block . For dynamically-defined Blocks , the Block type shall be
        the ONo of the Block's Factory. For the Root Block, the value of this
        property shall be 1. Deprecated in v3 of this class.

        This method has id ``3.1``.

        - :cpp:expr:`Type`: Output parameter.


    .. _ocablock_constructactionobject:

    .. cpp:function:: OcaStatus ConstructActionObject(OcaClassID ClassID, OcaList<OcaConstructionParameter> ConstructionParameters, OcaONo &ObjectNumber)

        Constructs an Action Object according to the given construction
        specification and adds it to the Block. Added in version 3 of this
        class.

        This method has id ``3.2``.

        - :cpp:expr:`ClassID`: Input parameter.


        - :cpp:expr:`ConstructionParameters`: Input parameter.


        - :cpp:expr:`ObjectNumber`: Output parameter.


    .. _ocablock_constructblockusingfactory:

    .. cpp:function:: OcaStatus ConstructBlockUsingFactory(OcaONo FactoryONo, OcaONo &ObjectNumber)

        Invokes a Block Factory (i.e. an **OcaBlockFactoryAgent** instance) to
        construct an instance of a Block inside this Block.

        This method has id ``3.3``.

        - :cpp:expr:`FactoryONo`: Input parameter.


        - :cpp:expr:`ObjectNumber`: Output parameter.


    .. _ocablock_deletemember:

    .. cpp:function:: OcaStatus DeleteMember(OcaONo ObjectNumber)

        Removes a Member from the Block and destroys the object. Deletes all
        Signal Paths that were attached to the object's Ports.

        This method has id ``3.4``.

        - :cpp:expr:`ObjectNumber`: Input parameter.


    .. _ocablock_getactionobjects:

    .. cpp:function:: OcaStatus GetActionObjects(OcaList<OcaObjectIdentification> &Objects)

        Gets the list of Action Objects in the block. Does not recurse inner
        Blocks. Each inner Block shall be included in the returned list as a
        single object -- its contents shall not be enumerated. Return data shall
        not list Dataset Objects. Previously named **GetMembers.**

        This method has id ``3.5``.

        - :cpp:expr:`Objects`: Output parameter.


    .. _ocablock_getactionobjectsrecursive:

    .. cpp:function:: OcaStatus GetActionObjectsRecursive(OcaList<OcaBlockMember> &Objects)

        Get a list of Member Descriptors (see datatype OcaBlockMember) that
        identify all the Action Objects in this Block and in all contained
        Blocks. Each contained Block shall be included in the returned list, and
        its contents shall be enumerated and returned in the list as well.
        Return data shall not list Dataset Objects. In the event that the size
        of the returned list exceeds the implementation limit, this method shall
        return the **OcaStatus** value **BufferOverflow**. Previously named
        **GetMembersRecursive.**

        This method has id ``3.6``.

        - :cpp:expr:`Objects`: Output parameter.


    .. _ocablock_addsignalpath:

    .. cpp:function:: OcaStatus AddSignalPath(OcaSignalPath Path, OcaID16 &Index)

        Adds a Signal Path to the Block.

        This method has id ``3.7``.

        - :cpp:expr:`Path`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


    .. _ocablock_deletesignalpath:

    .. cpp:function:: OcaStatus DeleteSignalPath(OcaID16 Index)

        Deletes a Signal Path from the block.

        This method has id ``3.8``.

        - :cpp:expr:`Index`: Input parameter.


    .. _ocablock_getsignalpaths:

    .. cpp:function:: OcaStatus GetSignalPaths(OcaMap<OcaID16, OcaSignalPath> &Members)

        Gets the map of Signal Paths in the Block. Does not recurse inner
        Blocks.

        This method has id ``3.9``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablock_getsignalpathsrecursive:

    .. cpp:function:: OcaStatus GetSignalPathsRecursive(OcaMap<OcaID16, OcaSignalPath> &SignalPaths)

        Gets the map of Signal Paths in the Block and all inner Blocks. In the
        event that the size of the returned data exceeds the implementation
        limit, this method shall return the **OcaStatus** value
        **BufferOverflow**.

        This method has id ``3.10``.

        - :cpp:expr:`SignalPaths`: Output parameter.


    .. _ocablock_getmostrecentparamsetidentifier:

    .. cpp:function:: OcaStatus GetMostRecentParamSetIdentifier(OcaLibVolIdentifier &Identifier)

        Gets the identifier of the ParamSet most recently applied to this Block.
        **Deprecated** in v3 of this class.

        This method has id ``3.11``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocablock_applyparamset:

    .. cpp:function:: OcaStatus ApplyParamSet(OcaLibVolIdentifier &Identifier)

        Applies the referenced ParamSet to this block, and sets the
        **MostRecentParamSetIdentifier** property. **Deprecated** in v3 of this
        class (OCA 1.5)** -** controllers should use the new **OcaDataset**
        method of storing ParamSets,

        This method has id ``3.12``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocablock_getcurrentparamsetdata:

    .. cpp:function:: OcaStatus GetCurrentParamSetData(OcaLibVolData_ParamSet &Data)

        Returns a ParamSet library volume data block which represents the
        current state of the block -- i.e. a "snapshot". **Deprecated** in v3 of
        this class (OCA 1.5)** -** controllers should use the new **OcaDataset**
        method of storing ParamSet, and use normal **OcaDataset** reading
        procedures for retrieving ParamSets.

        This method has id ``3.13``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocablock_storecurrentparamsetdata:

    .. cpp:function:: OcaStatus StoreCurrentParamSetData(OcaLibVolIdentifier Identifier)

        Stores a ParamSet library volume data block which represents the current
        state of the block. **Deprecated** in v3 of this class (OCA 1.5)** -**
        controllers should use the new **OcaDataset** method of storing
        ParamSets. If using the (current) OcaDataset mechanism, the dataset
        identified must have been created prior to calling this method.

        This method has id ``3.14``.

        - :cpp:expr:`Identifier`: Input parameter.


    .. _ocablock_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the Global Blocktype. If this Block has no Global Blocktype, the
        **Authority** field of the returned **GlobalType** parameter shall be
        zero. Added in version 2 of this class.

        This method has id ``3.15``.

        - :cpp:expr:`GlobalType`: Output parameter.


    .. _ocablock_getonomap:

    .. cpp:function:: OcaStatus GetONoMap(OcaMap<OcaProtoONo, OcaONo> &ONoMap)

        Gets the Block's ONo map. Added in version 2 of this class.

        This method has id ``3.16``.

        - :cpp:expr:`ONoMap`: Output parameter.


    .. _ocablock_findactionobjectsbyrole:

    .. cpp:function:: OcaStatus FindActionObjectsByRole(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaActionObjectSearchResultFlags ResultFlags, OcaList<OcaActionObjectSearchResult> &Result)

        Returns object identifications of all Action Objects in the Block that
        match the given Role search string and Class ID. Return data shall not
        list Dataset Objects. Replaces deprecated method **FindMembersByRole**.

        This method has id ``3.17``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findactionobjectsbyrolerecursive:

    .. cpp:function:: OcaStatus FindActionObjectsByRoleRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaActionObjectSearchResultFlags ResultFlags, OcaList<OcaActionObjectSearchResult> &Result)

        Returns descriptors of all Action Objects that match the given Role
        search string and Class ID. Searches this Block and all contained
        Blocks. Return data shall not list Dataset Objects. In the event that
        the size of the returned data exceeds the implementation limit, this
        method shall return the **OcaStatus** value **BufferOverflow**.

        This method has id ``3.18``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findactionobjectsbylabelrecursive:

    .. cpp:function:: OcaStatus FindActionObjectsByLabelRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaActionObjectSearchResultFlags ResultFlags, OcaList<OcaActionObjectSearchResult> &Result)

        Returns descriptors of all Action Objects that match the given Label
        search string and Class ID. Searches this Block and all contained
        Blocks. Return data shall not list Dataset Objects. In the event that
        the size of the returned data exceeds the implementation limit, this
        method shall return the **OcaStatus** value **BufferOverflow**.

        This method has id ``3.19``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findactionobjectsbyrolepath:

    .. cpp:function:: OcaStatus FindActionObjectsByRolePath(OcaRolePath SearchPath, OcaActionObjectSearchResultFlags ResultFlags, OcaList<OcaActionObjectSearchResult> &Result)

        Returns descriptors of all Action Objects with the given Role Path.
        Return data shall not list Dataset Objects.

        This method has id ``3.20``.

        - :cpp:expr:`SearchPath`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_getconfigurability:

    .. cpp:function:: OcaStatus GetConfigurability(OcaBlockConfigurability &Configurability)

        Gets the Block's Configurability.

        This method has id ``3.21``.

        - :cpp:expr:`Configurability`: Output parameter.


    .. _ocablock_getmostrecentparamdatasetono:

    .. cpp:function:: OcaStatus GetMostRecentParamDatasetONo(OcaONo &ONo)

        Gets the ONo of the paramDataset most recently applied to this Block.

        This method has id ``3.22``.

        - :cpp:expr:`ONo`: Output parameter.


    .. _ocablock_applyparamdataset:

    .. cpp:function:: OcaStatus ApplyParamDataset(OcaONo ONo)

        Applies the**** ParamDataset with the given ONo to this block, and sets
        the **MostRecentParamDatasetONo** property.

        This method has id ``3.23``.

        - :cpp:expr:`ONo`: Input parameter.


    .. _ocablock_storecurrentparameterdata:

    .. cpp:function:: OcaStatus StoreCurrentParameterData(OcaONo ONo)

        Stores current parameter values of this Block in the Dataset Object
        identified by the ONo parameter. The Dataset Object must exist - this
        method shall not create it.

        This method has id ``3.24``.

        - :cpp:expr:`ONo`: Input parameter.


    .. _ocablock_fetchcurrentparameterdata:

    .. cpp:function:: OcaStatus FetchCurrentParameterData(OcaLongBlob &Data)

        Returns current parameter values of this Block to the Controller in a
        single **OcaBlob**. Format of the parameter data shall be
        implementation-specific and not defined in this standard.

        This method has id ``3.25``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocablock_applyparameterdata:

    .. cpp:function:: OcaStatus ApplyParameterData(OcaLongBlob &Data)

        Applies the supplied parameter data to the Block. Format of the
        parameter data shall be implementation-specific and not defined in this
        standard. The implementation may elect to save the supplied data in a
        ParamDataset. If so, this method shall set the
        **MostRecentParamDatasetONo** property to the object number of this
        ParamDataset. If not, this method shall set
        **MostRecentParamDatasetONo** to zero.

        This method has id ``3.26``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocablock_constructdataset:

    .. cpp:function:: OcaStatus ConstructDataset(OcaClassID ClassID, OcaString Name, OcaMimeType Type, OcaUint64 MaxSize, OcaLongBlob InitialContents, OcaONo &ObjectNumber)

        Constructs a Dataset and its Dataset Object.

        This method has id ``3.27``.

        - :cpp:expr:`ClassID`: Input parameter.


        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`MaxSize`: Input parameter.


        - :cpp:expr:`InitialContents`: Input parameter.


        - :cpp:expr:`ObjectNumber`: Output parameter.


    .. _ocablock_duplicatedataset:

    .. cpp:function:: OcaStatus DuplicateDataset(OcaONo OldONo, OcaONo TargetBlockONo, OcaString NewName, OcaUint64 NewMaxSize, OcaONo &NewONo)

        Duplicates a Dataset and its Dataset Object.

        This method has id ``3.28``.

        - :cpp:expr:`OldONo`: Input parameter.


        - :cpp:expr:`TargetBlockONo`: Input parameter.


        - :cpp:expr:`NewName`: Input parameter.


        - :cpp:expr:`NewMaxSize`: Input parameter.


        - :cpp:expr:`NewONo`: Output parameter.


    .. _ocablock_getdatasetobjects:

    .. cpp:function:: OcaStatus GetDatasetObjects(OcaList<OcaObjectIdentification> &Objects)

        Returns identifiers of Dataset Objects in the Block. Shall not recurse
        inner Blocks. Return data shall not list Action Objects.

        This method has id ``3.29``.

        - :cpp:expr:`Objects`: Output parameter.


    .. _ocablock_getdatasetobjectsrecursive:

    .. cpp:function:: OcaStatus GetDatasetObjectsRecursive(OcaList<OcaBlockMember> &Objects)

        Returns descriptors of Dataset Objects in the Block and in contained
        Blocks. Return data shall not list Action Objects. In the event that the
        size of the returned data exceeds the implementation limit, this method
        shall return the **OcaStatus** value **BufferOverflow**.

        This method has id ``3.30``.

        - :cpp:expr:`Objects`: Output parameter.


    .. _ocablock_finddatasets:

    .. cpp:function:: OcaStatus FindDatasets(OcaString Name, OcaStringComparisonType NameComparisonType, OcaMimeType Type, OcaStringComparisonType TypeComparisonType, OcaList<OcaDatasetSearchResult> &Datasets)

        Returns descriptors of all Datasets in the block that match the given
        search terms. Note: If substring comparison type is selected, null
        search terms match anything. Return data shall not list Action Objects.

        This method has id ``3.31``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`TypeComparisonType`: Input parameter.


        - :cpp:expr:`Datasets`: Output parameter.


    .. _ocablock_finddatasetsrecursive:

    .. cpp:function:: OcaStatus FindDatasetsRecursive(OcaString Name, OcaStringComparisonType NameComparisonType, OcaMimeType Type, OcaStringComparisonType TypeComparisonType, OcaList<OcaDatasetSearchResult> &Datasets)

        Returns descriptors of all Datasets in this Block and all contained
        Blocks that match the given search terms. Note: If substring comparison
        type is selected, null search terms match anything. In the event that
        the size of the returned list exceeds the implementation limit, this
        method shall return the **OcaStatus** value **BufferOverflow**.

        This method has id ``3.32``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`TypeComparisonType`: Input parameter.


        - :cpp:expr:`Datasets`: Output parameter.


    .. _ocablock_getblockfactoryono:

    .. cpp:function:: OcaStatus GetBlockFactoryONo(OcaONo &ONo)

        Gets the value of property **BlockFactoryONo**

        This method has id ``3.33``.

        - :cpp:expr:`ONo`: Output parameter.


    Methods inherited from :ref:`ocaworker`:

    - :ref:`OcaWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaWorker::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaWorker::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaWorker::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaWorker::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaWorker::GetPath <ocaworker_getpath>`

    - :ref:`OcaWorker::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaWorker::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaWorker::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaWorker::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaWorker::SetPortName <ocaworker_setportname>`

