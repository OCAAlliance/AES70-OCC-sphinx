.. _ocablockfactory:

1.1.4  OcaBlockFactory
======================

Extends :ref:`OcaWorker <ocaworker>`.

.. cpp:class:: OcaBlockFactory: OcaWorker

    Factory to create custom block instances. Used only in reconfigurable
    devices. The idea is that you instantiate a factory once, populate it
    with proto-objects and proto-signal paths, then use it subsequently to
    instantiate identical blocks. In this context, **proto-object** means
    a prototype of a block member. Unbound objects are identified by
    **proto-object numbers (PONo's)** instead of actual object numbers.
    PONos are unique within the factory, and are converted to globally
    unique object numbers ONos) in all new block instances that the
    factory builds. Correspondingly, **proto-signal path** means a signal
    path expressed in terms of **PONos** rather than **ONos** . When the
    factory constructs a block, it converts all of its unbound signal
    paths to normal (bound) signal paths by mapping its **PONos** into
    **ONos** . The factory also holds a list of **proto-blockports** which
    are **OcaPorts** that are allocated to new blocks the factory builds.
    As well, the proto-objects in the factory may contain lists of their
    own proto-ports. Together, the factory's proto-ports and its members'
    proto-ports are used to define the factory's set of proto-signal
    paths. Factories may be predefined at time of device manufacture, or
    constructed "on the fly" by controllers. To **create a factory** , the
    controller calls a block's **CreateMember(...)** method with the
    **ClassID** of this class ( **OcaBlockFactory** ). Factories ignore
    which block creates them, so it makes no difference which block's
    **CreateMember(...)** method is used. It will usually make the most
    sense to use the Root Block's method. To add proto-objects,
    proto-ports, and proto-signal paths to a block factory, the controller
    calls the factory's **DefineProtoMember(...), DefineProtoPort(...),
    and DefineProtoSignalPath(...** ) methods, respectively.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaList<OcaProtoPort> ProtoPorts

        This property has id ``3.1``.

        List of proto-ports for built objects. The factory itself has no
        ports.

    .. cpp:member:: OcaList<OcaProtoObjectIdentification> ProtoMembers

        This property has id ``3.2``.

        List of prot-object identifiers of proto-members in the block.

    .. cpp:member:: OcaMap<OcaUint16, OcaProtoSignalPath> ProtoSignalPaths

        This property has id ``3.3``.

        List of proto-signal paths in the block.

    .. cpp:member:: OcaGlobalTypeIdentifier GlobalType

        This property has id ``3.4``.

        Global block type identifier for reusable blocks. **Added in version 2
        of this class.**

    .. cpp:function:: OcaStatus DefineProtoPort(OcaString name, OcaPortMode portmode, OcaProtoPortID &id)

        This method has id ``3.1``.

        Defines a proto-port in the factory. If proto-port already exists, it
        is replaced with the one from this call. The return value indicates
        whether the proto-port was successfully added.

        :param OcaString name: Input parameter.
        :param OcaPortMode portmode: Input parameter.
        :param OcaProtoPortID id: Output parameter.

    .. cpp:function:: OcaStatus UndefineProtoPort(OcaProtoPortID ProtoPortID)

        This method has id ``3.2``.

        Deletes a proto-port from the factory. The return value indicates
        whether the proto-port was successfully deleted.

        :param OcaProtoPortID ProtoPortID: Input parameter.

    .. cpp:function:: OcaStatus GetProtoPorts(OcaList<OcaProtoPort> &Ports)

        This method has id ``3.3``.

        Gets the factory's list of proto-ports. The return value indicates
        whether the list was successfully retrieved.

        :param OcaList<OcaProtoPort> Ports: Output parameter.

    .. cpp:function:: OcaStatus DefineProtoMember(OcaClassID ClassIdentification, ConstructionParameterDataType ConstructionParameters, OcaProtoONo &ProtoObjectNumber)

        This method has id ``3.4``.

        Defines a proto-member of the given class in the factory. The most
        current version of the class is used. The return value indicates
        whether the proto-member was successfully defined.

        :param OcaClassID ClassIdentification: Input parameter.
        :param ConstructionParameterDataType ConstructionParameters: Input parameter.
        :param OcaProtoONo ProtoObjectNumber: Output parameter.

    .. cpp:function:: OcaStatus DefineProtoMemberUsingFactory(OcaONo FactoryONo, OcaProtoONo &ProtoObjectNumber)

        This method has id ``3.5``.

        Defines a proto-member which will be instantiated by a specified
        factory when the block is built. The return value indicates whether
        the proto-member was successfully defined.

        :param OcaONo FactoryONo: Input parameter.
        :param OcaProtoONo ProtoObjectNumber: Output parameter.

    .. cpp:function:: OcaStatus UndefineProtoMember(OcaProtoONo ProtoObjectNumber)

        This method has id ``3.6``.

        Deletes a proto-member from the factory. Deletes all proto-signal
        paths attached to its ports. The return value indicates whether the
        member was successfully deleted.

        :param OcaProtoONo ProtoObjectNumber: Input parameter.

    .. cpp:function:: OcaStatus GetProtoMembers(OcaList<OcaProtoObjectIdentification> &Members)

        This method has id ``3.7``.

        Gets the factory's list of proto-members. Does not recurse inner
        proto-blocks. The return value indicates whether the list was
        successfully retrieved.

        :param OcaList<OcaProtoObjectIdentification> Members: Output parameter.

    .. cpp:function:: OcaStatus DefineProtoSignalPath(OcaProtoSignalPath Path, OcaUint16 &Index)

        This method has id ``3.8``.

        Defines a proto-signal path in the factory. The return value indicates
        whether the proto-signal path was successfully defined.

        :param OcaProtoSignalPath Path: Input parameter.
        :param OcaUint16 Index: Output parameter.

    .. cpp:function:: OcaStatus UndefineProtoSignalPath(OcaUint16 &Index)

        This method has id ``3.9``.

        Deletes a proto-signal path from the factory. The return value
        indicates whether the signal path was successfully added.

        :param OcaUint16 Index: Output parameter.

    .. cpp:function:: OcaStatus GetProtoSignalPaths(OcaMap<OcaUint16, OcaProtoSignalPath> &Members)

        This method has id ``3.10``.

        Gets the factory's list of proto-signal paths. Map key is proto-signal
        path ID. Does not recurse inner proto-blocks. The return value
        indicates whether the list was successfully retrieved.

        :param OcaMap<OcaUint16, OcaProtoSignalPath> Members: Output parameter.

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        This method has id ``3.11``.

        Gets the global type identifier for blocks created by this factory.
        The return value indicates whether the identifier was successfully
        retrieved. **Added in version 2 of this class.**

        :param OcaGlobalTypeIdentifier GlobalType: Output parameter.

    .. cpp:function:: OcaStatus SetGlobalType(OcaGlobalTypeIdentifier GlobalType)

        This method has id ``3.12``.

        Sets the global type identifier for blocks created by this factory.
        The return value indicates whether the identifier was successfully
        set. **Added in version 2 of this class.**

        :param OcaGlobalTypeIdentifier GlobalType: Input parameter.

