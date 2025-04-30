.. _ocablock:

1.1.3  OcaBlock
===============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaBlock <ocablock>`

.. cpp:class:: OcaBlock: OcaWorker

    A block is an object with three aspects: - It can contain other blocks. - It
    can contain workers. - It can contain agents. - It can contain data
    networks. - It can contain application networks. - It has a signal flow
    topology. We refer to an object inside a block as a **member** of that
    block. We refer to the block which contains an object as the object's
    **container.1** Normally, a block contains a set of members that together
    function as a processing unit -- for example, a crossover channel or mixer
    strip.

    **Properties**:


    .. _ocablock_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.3"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocablock_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocablock_type:

    .. cpp:member:: const OcaONo Type

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

        Library volume identifier of the paramset most recently applied to this
        block.

        This property has id ``3.4``.

    .. _ocablock_globaltype:

    .. cpp:member:: const OcaGlobalTypeIdentifier GlobalType

        Global block type identifier for reusable blocks. **Added in version 2
        of this class.**

        This property has id ``3.5``.

    .. _ocablock_onomap:

    .. cpp:member:: const OcaMap<OcaProtoONo, OcaONo> ONoMap

        For blocks constructed by factories. Map that indicates the actual ONos
        allocated to the constructing OcaBlockFactory's prototype ONos. Key is
        prototype ONo, value is actual ONo. **Added in version 2 of this
        class.**

        This property has id ``3.6``.

    Properties inherited from :ref:`ocaworker`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`


    **Methods**:


    .. _ocablock_gettype:

    .. cpp:function:: OcaStatus GetType(OcaONo &Type)

        Gets the block type. For statically-defined blocks, the block type is a
        Uint32 with a value corresponding to the unique configuration of this
        block. For dynamically-defined blocks, the block type is the object
        number of the block's factory. For the root block, the value of this
        property is 1.

        This method has id ``3.1``.

        - :cpp:expr:`Type`: Output parameter.


    .. _ocablock_constructmember:

    .. cpp:function:: OcaStatus ConstructMember(OcaClassID ClassID, variant ConstructionParameters, OcaONo &ObjectNumber)

        Constructs an object according to the given construction specification
        and adds it to the block. The return value indicates whether the member
        was successfully created and added.

        This method has id ``3.2``.

        - :cpp:expr:`ClassID`: Input parameter.


        - :cpp:expr:`ConstructionParameters`: Input parameter.


        - :cpp:expr:`ObjectNumber`: Output parameter.


    .. _ocablock_constructmemberusingfactory:

    .. cpp:function:: OcaStatus ConstructMemberUsingFactory(OcaONo FactoryONo, OcaONo &ObjectNumber)

        Invokes a factory to construct an instance of the given class, then adds
        it to the block. The return value indicates whether the member was
        successfully created and added.

        This method has id ``3.3``.

        - :cpp:expr:`FactoryONo`: Input parameter.


        - :cpp:expr:`ObjectNumber`: Output parameter.


    .. _ocablock_deletemember:

    .. cpp:function:: OcaStatus DeleteMember(OcaONo ObjectNumber)

        Removes a member from the block and destroys the object. . Deletes all
        signal paths attached to its ports. The return value indicates whether
        the member was successfully removed and destroyed.

        This method has id ``3.4``.

        - :cpp:expr:`ObjectNumber`: Input parameter.


    .. _ocablock_getmembers:

    .. cpp:function:: OcaStatus GetMembers(OcaList<OcaObjectIdentification> &Members)

        Gets the list of block members. Does not recurse inner blocks. Each
        inner block is included in the returned list as a single object -- its
        contents are not enumerated. The return value indicates whether the list
        was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablock_getmembersrecursive:

    .. cpp:function:: OcaStatus GetMembersRecursive(OcaList<OcaBlockMember> &Members)

        Gets the list of block members. Recurses inner blocks. Each inner block
        is included in the returned list as a single object, amd its contents
        are enumerated. The return value indicates whether the list was
        successfully retrieved.

        This method has id ``3.6``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablock_addsignalpath:

    .. cpp:function:: OcaStatus AddSignalPath(OcaSignalPath Path, OcaUint16 &Index)

        Adds a signal path to the block. The return value indicates whether the
        signal path was successfully added.

        This method has id ``3.7``.

        - :cpp:expr:`Path`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


    .. _ocablock_deletesignalpath:

    .. cpp:function:: OcaStatus DeleteSignalPath(OcaUint16 Index)

        Deletes a signal path from the block. The return value indicates whether
        the signal path was successfully added.

        This method has id ``3.8``.

        - :cpp:expr:`Index`: Input parameter.


    .. _ocablock_getsignalpaths:

    .. cpp:function:: OcaStatus GetSignalPaths(OcaMap<OcaUint16, OcaSignalPath> &Members)

        Gets the map of signal paths in the block. Does not recurse inner
        blocks. The return value indicates whether the list was successfully
        retrieved.

        This method has id ``3.9``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablock_getsignalpathsrecursive:

    .. cpp:function:: OcaStatus GetSignalPathsRecursive(OcaMap<OcaUint16, OcaSignalPath> &Members)

        Gets the mapof signal paths in the block. Recurses inner blocks. The
        return value indicates whether the list was successfully retrieved.

        This method has id ``3.10``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablock_getmostrecentparamsetidentifier:

    .. cpp:function:: OcaStatus GetMostRecentParamSetIdentifier(OcaLibVolIdentifier &Identifier)

        Gets the identifier of the paramset most recently applied to this block.

        This method has id ``3.11``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocablock_applyparamset:

    .. cpp:function:: OcaStatus ApplyParamSet(OcaLibVolIdentifier &Identifier)

        Applies the referenced paramset to this block, and sets the
        MostRecentParamSet property. The return value indicates whether the
        paramset was successfully applied.

        This method has id ``3.12``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocablock_getcurrentparamsetdata:

    .. cpp:function:: OcaStatus GetCurrentParamSetData(OcaLibVolData_ParamSet &Data)

        Returns a paramset library volume data block which represents the
        current state of the block -- i.e. a "snapshot".

        This method has id ``3.13``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocablock_storecurrentparamsetdata:

    .. cpp:function:: OcaStatus StoreCurrentParamSetData(OcaLibVolIdentifier LibVolIdentifier)

        Stores a paramset library volume data block which represents the current
        state of the block ("snapshot") in the given library. **Replaces** the
        library volume at the specified LibVolIdentifier.

        This method has id ``3.14``.

        - :cpp:expr:`LibVolIdentifier`: Input parameter.


    .. _ocablock_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the global blocktype. The return value indicates whether the type
        was successfully retrieved. If this block has no global blocktype, the
        **Authority** field of the returned **GlobalType** parameter will be
        zero. **Added in version 2 of this class.**

        This method has id ``3.15``.

        - :cpp:expr:`GlobalType`: Output parameter.


    .. _ocablock_getonomap:

    .. cpp:function:: OcaStatus GetONoMap(OcaMap<OcaProtoONo, OcaONo> &ONoMap)

        Gets the block's ONo map. The return value indicates whether the map was
        successfully retrieved. **Added in version 2 of this class.**

        This method has id ``3.16``.

        - :cpp:expr:`ONoMap`: Output parameter.


    .. _ocablock_findobjectsbyrole:

    .. cpp:function:: OcaStatus FindObjectsByRole(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns object identifications of all objects in the block that match
        the given Role search string and Class ID. Return value indicates
        whether the method succeeded. **Added in version 2 of this class.**

        This method has id ``3.17``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findobjectsbyrolerecursive:

    .. cpp:function:: OcaStatus FindObjectsByRoleRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Role search string and Class ID.
        **Added in version 2 of this class.**

        This method has id ``3.18``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findobjectsbylabelrecursive:

    .. cpp:function:: OcaStatus FindObjectsByLabelRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Label search string and Class ID.
        **Added in version 2 of this class.**

        This method has id ``3.19``.

        - :cpp:expr:`SearchName`: Input parameter.


        - :cpp:expr:`NameComparisonType`: Input parameter.


        - :cpp:expr:`SearchClassID`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    .. _ocablock_findobjectsbypath:

    .. cpp:function:: OcaStatus FindObjectsByPath(OcaNamePath SearchPath, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        Returns object identifications of all objects with the given name path.
        **Added in version 2 of this class.**

        This method has id ``3.20``.

        - :cpp:expr:`SearchPath`: Input parameter.


        - :cpp:expr:`ResultFlags`: Input parameter.


        - :cpp:expr:`Result`: Output parameter.


    Methods inherited from :ref:`ocaworker`:

    - :ref:`OcaWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaWorker::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaWorker::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaWorker::SetPortName <ocaworker_setportname>`

    - :ref:`OcaWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaWorker::GetPath <ocaworker_getpath>`

