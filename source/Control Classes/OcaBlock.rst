.. _ocablock:

1.1.3  OcaBlock
===============

Extends :ref:`OcaWorker <ocaworker>`.

.. cpp:class:: OcaBlock: OcaWorker

    A block is an object with three aspects: - It can contain other
    blocks. - It can contain workers. - It can contain agents. - It can
    contain data networks. - It can contain application networks. - It has
    a signal flow topology. We refer to an object inside a block as a
    **member** of that block. We refer to the block which contains an
    object as the object's **container.** **1** Normally, a block contains
    a set of members that together function as a processing unit -- for
    example, a crossover channel or mixer strip.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaONo Type

        This property has id ``3.1``.

        Readonly block type. For statically-defined blocks, this value is a
        Uint32 with a value corresponding to the unique configuration of this
        block. For dynamically-defined blocks, this value is the object number
        of the block's factory. For the root block, the value of this property
        is 1.

    .. cpp:member:: OcaList<OcaObjectIdentification> Members

        This property has id ``3.2``.

        List of members in the block.

    .. cpp:member:: OcaMap<OcaUint16, OcaSignalPath> SignalPaths

        This property has id ``3.3``.

        List of signal paths in the block.

    .. cpp:member:: OcaLibVolIdentifier MostRecentParamSetIdentifier

        This property has id ``3.4``.

        Library volume identifier of the paramset most recently applied to
        this block.

    .. cpp:member:: OcaGlobalTypeIdentifier GlobalType

        This property has id ``3.5``.

        Global block type identifier for reusable blocks. **Added in version 2
        of this class.**

    .. cpp:member:: OcaMap<OcaProtoONo, OcaONo> ONoMap

        This property has id ``3.6``.

        For blocks constructed by factories. Map that indicates the actual
        ONos allocated to the constructing OcaBlockFactory's prototype ONos.
        Key is prototype ONo, value is actual ONo. **Added in version 2 of
        this class.**

    .. cpp:function:: OcaStatus GetType(OcaONo &Type)

        This method has id ``3.1``.

        Gets the block type. For statically-defined blocks, the block type is
        a Uint32 with a value corresponding to the unique configuration of
        this block. For dynamically-defined blocks, the block type is the
        object number of the block's factory. For the root block, the value of
        this property is 1.

        :param OcaONo Type: Output parameter.

    .. cpp:function:: OcaStatus ConstructMember(OcaClassID ClassID, variant[n] ConstructionParameters, OcaONo &ObjectNumber)

        This method has id ``3.2``.

        Constructs an object according to the given construction specification
        and adds it to the block. The return value indicates whether the
        member was successfully created and added.

        :param OcaClassID ClassID: Input parameter.
        :param variant[n] ConstructionParameters: Input parameter.
        :param OcaONo ObjectNumber: Output parameter.

    .. cpp:function:: OcaStatus ConstructMemberUsingFactory(OcaONo FactoryONo, OcaONo &ObjectNumber)

        This method has id ``3.3``.

        Invokes a factory to construct an instance of the given class, then
        adds it to the block. The return value indicates whether the member
        was successfully created and added.

        :param OcaONo FactoryONo: Input parameter.
        :param OcaONo ObjectNumber: Output parameter.

    .. cpp:function:: OcaStatus DeleteMember(OcaONo ObjectNumber)

        This method has id ``3.4``.

        Removes a member from the block and destroys the object. . Deletes all
        signal paths attached to its ports. The return value indicates whether
        the member was successfully removed and destroyed.

        :param OcaONo ObjectNumber: Input parameter.

    .. cpp:function:: OcaStatus GetMembers(OcaList<OcaObjectIdentification> &Members)

        This method has id ``3.5``.

        Gets the list of block members. Does not recurse inner blocks. Each
        inner block is included in the returned list as a single object -- its
        contents are not enumerated. The return value indicates whether the
        list was successfully retrieved.

        :param OcaList<OcaObjectIdentification> Members: Output parameter.

    .. cpp:function:: OcaStatus GetMembersRecursive(OcaList<OcaBlockMember> &Members)

        This method has id ``3.6``.

        Gets the list of block members. Recurses inner blocks. Each inner
        block is included in the returned list as a single object, amd its
        contents are enumerated. The return value indicates whether the list
        was successfully retrieved.

        :param OcaList<OcaBlockMember> Members: Output parameter.

    .. cpp:function:: OcaStatus AddSignalPath(OcaSignalPath Path, OcaUint16 &Index)

        This method has id ``3.7``.

        Adds a signal path to the block. The return value indicates whether
        the signal path was successfully added.

        :param OcaSignalPath Path: Input parameter.
        :param OcaUint16 Index: Output parameter.

    .. cpp:function:: OcaStatus DeleteSignalPath(OcaUint16 Index)

        This method has id ``3.8``.

        Deletes a signal path from the block. The return value indicates
        whether the signal path was successfully added.

        :param OcaUint16 Index: Input parameter.

    .. cpp:function:: OcaStatus GetSignalPaths(OcaMap<OcaUint16, OcaSignalPath> &Members)

        This method has id ``3.9``.

        Gets the map of signal paths in the block. Does not recurse inner
        blocks. The return value indicates whether the list was successfully
        retrieved.

        :param OcaMap<OcaUint16, OcaSignalPath> Members: Output parameter.

    .. cpp:function:: OcaStatus GetSignalPathsRecursive(OcaMap<OcaUint16, OcaSignalPath> &Members)

        This method has id ``3.10``.

        Gets the mapof signal paths in the block. Recurses inner blocks. The
        return value indicates whether the list was successfully retrieved.

        :param OcaMap<OcaUint16, OcaSignalPath> Members: Output parameter.

    .. cpp:function:: OcaStatus GetMostRecentParamSetIdentifier(OcaLibVolIdentifier &Identifier)

        This method has id ``3.11``.

        Gets the identifier of the paramset most recently applied to this
        block.

        :param OcaLibVolIdentifier Identifier: Output parameter.

    .. cpp:function:: OcaStatus ApplyParamSet(OcaLibVolIdentifier &Identifier)

        This method has id ``3.12``.

        Applies the referenced paramset to this block, and sets the
        MostRecentParamSet property. The return value indicates whether the
        paramset was successfully applied.

        :param OcaLibVolIdentifier Identifier: Output parameter.

    .. cpp:function:: OcaStatus GetCurrentParamSetData(OcaLibVolData_ParamSet &Data)

        This method has id ``3.13``.

        Returns a paramset library volume data block which represents the
        current state of the block -- i.e. a "snapshot".

        :param OcaLibVolData_ParamSet Data: Output parameter.

    .. cpp:function:: OcaStatus StoreCurrentParamSetData(OcaLibVolIdentifier LibVolIdentifier)

        This method has id ``3.14``.

        Stores a paramset library volume data block which represents the
        current state of the block ("snapshot") in the given library.
        **Replaces** the library volume at the specified LibVolIdentifier.

        :param OcaLibVolIdentifier LibVolIdentifier: Input parameter.

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        This method has id ``3.15``.

        Gets the global blocktype. The return value indicates whether the type
        was successfully retrieved. If this block has no global blocktype, the
        **Authority** field of the returned **GlobalType** parameter will be
        zero. **Added in version 2 of this class.**

        :param OcaGlobalTypeIdentifier GlobalType: Output parameter.

    .. cpp:function:: OcaStatus GetONoMap(OcaMap<OcaProtoONo, OcaONo> &ONoMap)

        This method has id ``3.16``.

        Gets the block's ONo map. The return value indicates whether the map
        was successfully retrieved. **Added in version 2 of this class.**

        :param OcaMap<OcaProtoONo, OcaONo> ONoMap: Output parameter.

    .. cpp:function:: OcaStatus FindObjectsByRole(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        This method has id ``3.17``.

        Returns object identifications of all objects in the block that match
        the given Role search string and Class ID. Return value indicates
        whether the method succeeded. **Added in version 2 of this class.**

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. cpp:function:: OcaStatus FindObjectsByRoleRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        This method has id ``3.18``.

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Role search string and Class ID.
        **Added in version 2 of this class.**

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. cpp:function:: OcaStatus FindObjectsByPath(OcaNamePath SearchPath, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        This method has id ``3.20``.

        Returns object identifications of all objects with the given name
        path. **Added in version 2 of this class.**

        :param OcaNamePath SearchPath: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

    .. cpp:function:: OcaStatus FindObjectsByLabelRecursive(OcaString SearchName, OcaStringComparisonType NameComparisonType, OcaClassID SearchClassID, OcaObjectSearchResultFlags ResultFlags, OcaList<OcaObjectSearchResult> &Result)

        This method has id ``3.19``.

        Returns block member descriptors of all objects in the block and all
        contained blocks that match the given Label search string and Class
        ID. **Added in version 2 of this class.**

        :param OcaString SearchName: Input parameter.
        :param OcaStringComparisonType NameComparisonType: Input parameter.
        :param OcaClassID SearchClassID: Input parameter.
        :param OcaObjectSearchResultFlags ResultFlags: Input parameter.
        :param OcaList<OcaObjectSearchResult> Result: Output parameter.

