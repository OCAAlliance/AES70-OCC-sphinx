.. _ocablock:

1.1.3  OcaBlock
===============

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaBlock <ocablock>` 

.. cpp:class:: OcaBlock: OcaWorker

    A block is an object with three aspects: - It can contain other
    blocks. - It can contain workers. - It can contain agents. - It can
    contain data networks. - It can contain application networks. - It has
    a signal flow topology. We refer to an object inside a block as a
    **member** of that block. We refer to the block which contains an
    object as the object's **container.** **1** Normally, a block contains
    a set of members that together function as a processing unit -- for
    example, a crossover channel or mixer strip.

    **Properties**:

    .. _ocablock_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocablock_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocablock_type:

    .. cpp:member:: OcaONo Type

        Readonly block type. For statically-defined blocks, this value is a
        Uint32 with a value corresponding to the unique configuration of this
        block. For dynamically-defined blocks, this value is the object number
        of the block's factory. For the root block, the value of this property
        is 1.

        This property has id ``3.1``.

    .. _ocablock_members:

    .. cpp:member:: OcaList<OcaObjectIdentification> Members

        List of members in the block.

        This property has id ``3.2``.

    .. _ocablock_signalpaths:

    .. cpp:member:: OcaMap<OcaUint16, OcaSignalPath> SignalPaths

        List of signal paths in the block.

        This property has id ``3.3``.

    .. _ocablock_mostrecentparamsetidentifier:

    .. cpp:member:: OcaLibVolIdentifier MostRecentParamSetIdentifier

        Library volume identifier of the paramset most recently applied to
        this block.

        This property has id ``3.4``.

    .. _ocablock_globaltype:

    .. cpp:member:: OcaGlobalTypeIdentifier GlobalType

        Global block type identifier for reusable blocks. **Added in version 2
        of this class.**

        This property has id ``3.5``.

    .. _ocablock_onomap:

    .. cpp:member:: OcaMap<OcaProtoONo, OcaONo> ONoMap

        For blocks constructed by factories. Map that indicates the actual
        ONos allocated to the constructing OcaBlockFactory's prototype ONos.
        Key is prototype ONo, value is actual ONo. **Added in version 2 of
        this class.**

        This property has id ``3.6``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocablock_gettype:

    .. cpp:function:: OcaStatus GetType(OcaONo &Type)

        Gets the block type. For statically-defined blocks, the block type is
        a Uint32 with a value corresponding to the unique configuration of
        this block. For dynamically-defined blocks, the block type is the
        object number of the block's factory. For the root block, the value of
        this property is 1.

        This method has id ``3.1``.

        :param OcaONo Type: Output parameter.

    .. _ocablock_constructmember:

    .. cpp:function:: OcaStatus ConstructMember(OcaClassID ClassID, variant[n] ConstructionParameters, OcaONo &ObjectNumber)

        Constructs an object according to the given construction specification
        and adds it to the block. The return value indicates whether the
        member was successfully created and added.

        This method has id ``3.2``.

        :param OcaClassID ClassID: Input parameter.
        :param variant[n] ConstructionParameters: Input parameter.
        :param OcaONo ObjectNumber: Output parameter.

    .. _ocablock_constructmemberusingfactory:

    .. cpp:function:: OcaStatus ConstructMemberUsingFactory(OcaONo FactoryONo, OcaONo &ObjectNumber)

        Invokes a factory to construct an instance of the given class, then
        adds it to the block. The return value indicates whether the member
        was successfully created and added.

        This method has id ``3.3``.

        :param OcaONo FactoryONo: Input parameter.
        :param OcaONo ObjectNumber: Output parameter.

    .. _ocablock_deletemember:

    .. cpp:function:: OcaStatus DeleteMember(OcaONo ObjectNumber)

        Removes a member from the block and destroys the object. . Deletes all
        signal paths attached to its ports. The return value indicates whether
        the member was successfully removed and destroyed.

        This method has id ``3.4``.

        :param OcaONo ObjectNumber: Input parameter.

    .. _ocablock_getmembers:

    .. cpp:function:: OcaStatus GetMembers(OcaList<OcaObjectIdentification> &Members)

        Gets the list of block members. Does not recurse inner blocks. Each
        inner block is included in the returned list as a single object -- its
        contents are not enumerated. The return value indicates whether the
        list was successfully retrieved.

        This method has id ``3.5``.

        :param OcaList<OcaObjectIdentification> Members: Output parameter.

    .. _ocablock_getmembersrecursive:

    .. cpp:function:: OcaStatus GetMembersRecursive(OcaList<OcaBlockMember> &Members)

        Gets the list of block members. Recurses inner blocks. Each inner
        block is included in the returned list as a single object, amd its
        contents are enumerated. The return value indicates whether the list
        was successfully retrieved.

        This method has id ``3.6``.

        :param OcaList<OcaBlockMember> Members: Output parameter.

    .. _ocablock_addsignalpath:

    .. cpp:function:: OcaStatus AddSignalPath(OcaSignalPath Path, OcaUint16 &Index)

        Adds a signal path to the block. The return value indicates whether
        the signal path was successfully added.

        This method has id ``3.7``.

        :param OcaSignalPath Path: Input parameter.
        :param OcaUint16 Index: Output parameter.

    .. _ocablock_deletesignalpath:

    .. cpp:function:: OcaStatus DeleteSignalPath(OcaUint16 Index)

        Deletes a signal path from the block. The return value indicates
        whether the signal path was successfully added.

        This method has id ``3.8``.

        :param OcaUint16 Index: Input parameter.

    .. _ocablock_getsignalpaths:

    .. cpp:function:: OcaStatus GetSignalPaths(OcaMap<OcaUint16, OcaSignalPath> &Members)

        Gets the map of signal paths in the block. Does not recurse inner
        blocks. The return value indicates whether the list was successfully
        retrieved.

        This method has id ``3.9``.

        :param OcaMap<OcaUint16, OcaSignalPath> Members: Output parameter.

    .. _ocablock_getsignalpathsrecursive:

    .. cpp:function:: OcaStatus GetSignalPathsRecursive(OcaMap<OcaUint16, OcaSignalPath> &Members)

        Gets the mapof signal paths in the block. Recurses inner blocks. The
        return value indicates whether the list was successfully retrieved.

        This method has id ``3.10``.

        :param OcaMap<OcaUint16, OcaSignalPath> Members: Output parameter.

    .. _ocablock_getmostrecentparamsetidentifier:

    .. cpp:function:: OcaStatus GetMostRecentParamSetIdentifier(OcaLibVolIdentifier &Identifier)

        Gets the identifier of the paramset most recently applied to this
        block.

        This method has id ``3.11``.

        :param OcaLibVolIdentifier Identifier: Output parameter.

    .. _ocablock_applyparamset:

    .. cpp:function:: OcaStatus ApplyParamSet(OcaLibVolIdentifier &Identifier)

        Applies the referenced paramset to this block, and sets the
        MostRecentParamSet property. The return value indicates whether the
        paramset was successfully applied.

        This method has id ``3.12``.

        :param OcaLibVolIdentifier Identifier: Output parameter.

    .. _ocablock_getcurrentparamsetdata:

    .. cpp:function:: OcaStatus GetCurrentParamSetData(OcaLibVolData_ParamSet &Data)

        Returns a paramset library volume data block which represents the
        current state of the block -- i.e. a "snapshot".

        This method has id ``3.13``.

        :param OcaLibVolData_ParamSet Data: Output parameter.

    .. _ocablock_storecurrentparamsetdata:

    .. cpp:function:: OcaStatus StoreCurrentParamSetData(OcaLibVolIdentifier LibVolIdentifier)

        Stores a paramset library volume data block which represents the
        current state of the block ("snapshot") in the given library.
        **Replaces** the library volume at the specified LibVolIdentifier.

        This method has id ``3.14``.

        :param OcaLibVolIdentifier LibVolIdentifier: Input parameter.

    .. _ocablock_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the global blocktype. The return value indicates whether the type
        was successfully retrieved. If this block has no global blocktype, the
        **Authority** field of the returned **GlobalType** parameter will be
        zero. **Added in version 2 of this class.**

        This method has id ``3.15``.

        :param OcaGlobalTypeIdentifier GlobalType: Output parameter.

    .. _ocablock_getonomap:

    .. cpp:function:: OcaStatus GetONoMap(OcaMap<OcaProtoONo, OcaONo> &ONoMap)

        Gets the block's ONo map. The return value indicates whether the map
        was successfully retrieved. **Added in version 2 of this class.**

        This method has id ``3.16``.

        :param OcaMap<OcaProtoONo, OcaONo> ONoMap: Output parameter.

    .. _ocablock_findobjectsbyrole:

    .. cpp:function:: OcaStatus FindObjectsByRole(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns object identifications of all objects in the block that match
        the given Role search string and Class ID. Return value indicates
        whether the method succeeded. **Added in version 2 of this class.**

        This method has id ``3.17``.

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. _ocablock_findobjectsbyrolerecursive:

    .. cpp:function:: OcaStatus FindObjectsByRoleRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Role search string and Class ID.
        **Added in version 2 of this class.**

        This method has id ``3.18``.

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. _ocablock_findobjectsbypath:

    .. cpp:function:: OcaStatus FindObjectsByPath(OcaNamePath SearchPath, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns object identifications of all objects with the given name
        path. **Added in version 2 of this class.**

        This method has id ``3.20``.

        :param OcaNamePath SearchPath: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. _ocablock_findobjectsbylabelrecursive:

    .. cpp:function:: OcaStatus FindObjectsByLabelRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Label search string and Class
        ID. **Added in version 2 of this class.**

        This method has id ``3.19``.

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.


    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


