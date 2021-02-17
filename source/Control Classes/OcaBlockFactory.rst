.. _ocablockfactory:

1.1.4  OcaBlockFactory
======================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaBlockFactory <ocablockfactory>` 

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

    **Properties**:

    .. _ocablockfactory_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocablockfactory_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocablockfactory_protoports:

    .. cpp:member:: OcaList<OcaProtoPort> ProtoPorts

        List of proto-ports for built objects. The factory itself has no
        ports.

        This property has id ``3.1``.

    .. _ocablockfactory_protomembers:

    .. cpp:member:: OcaList<OcaProtoObjectIdentification> ProtoMembers

        List of prot-object identifiers of proto-members in the block.

        This property has id ``3.2``.

    .. _ocablockfactory_protosignalpaths:

    .. cpp:member:: OcaMap<OcaUint16, OcaProtoSignalPath> ProtoSignalPaths

        List of proto-signal paths in the block.

        This property has id ``3.3``.

    .. _ocablockfactory_globaltype:

    .. cpp:member:: OcaGlobalTypeIdentifier GlobalType

        Global block type identifier for reusable blocks. **Added in version 2
        of this class.**

        This property has id ``3.4``.

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

    .. _ocablockfactory_defineprotoport:

    .. cpp:function:: OcaStatus DefineProtoPort(OcaString name, OcaPortMode portmode, OcaProtoPortID &id)

        Defines a proto-port in the factory. If proto-port already exists, it
        is replaced with the one from this call. The return value indicates
        whether the proto-port was successfully added.

        This method has id ``3.1``.

        :param OcaString name: Input parameter.
        :param OcaPortMode portmode: Input parameter.
        :param OcaProtoPortID id: Output parameter.

    .. _ocablockfactory_undefineprotoport:

    .. cpp:function:: OcaStatus UndefineProtoPort(OcaProtoPortID ProtoPortID)

        Deletes a proto-port from the factory. The return value indicates
        whether the proto-port was successfully deleted.

        This method has id ``3.2``.

        :param OcaProtoPortID ProtoPortID: Input parameter.

    .. _ocablockfactory_getprotoports:

    .. cpp:function:: OcaStatus GetProtoPorts(OcaList<OcaProtoPort> &Ports)

        Gets the factory's list of proto-ports. The return value indicates
        whether the list was successfully retrieved.

        This method has id ``3.3``.

        :param OcaList<OcaProtoPort> Ports: Output parameter.

    .. _ocablockfactory_defineprotomember:

    .. cpp:function:: OcaStatus DefineProtoMember(OcaClassID ClassIdentification, ConstructionParameterDataType ConstructionParameters, OcaProtoONo &ProtoObjectNumber)

        Defines a proto-member of the given class in the factory. The most
        current version of the class is used. The return value indicates
        whether the proto-member was successfully defined.

        This method has id ``3.4``.

        :param OcaClassID ClassIdentification: Input parameter.
        :param ConstructionParameterDataType ConstructionParameters: Input parameter.
        :param OcaProtoONo ProtoObjectNumber: Output parameter.

    .. _ocablockfactory_defineprotomemberusingfactory:

    .. cpp:function:: OcaStatus DefineProtoMemberUsingFactory(OcaONo FactoryONo, OcaProtoONo &ProtoObjectNumber)

        Defines a proto-member which will be instantiated by a specified
        factory when the block is built. The return value indicates whether
        the proto-member was successfully defined.

        This method has id ``3.5``.

        :param OcaONo FactoryONo: Input parameter.
        :param OcaProtoONo ProtoObjectNumber: Output parameter.

    .. _ocablockfactory_undefineprotomember:

    .. cpp:function:: OcaStatus UndefineProtoMember(OcaProtoONo ProtoObjectNumber)

        Deletes a proto-member from the factory. Deletes all proto-signal
        paths attached to its ports. The return value indicates whether the
        member was successfully deleted.

        This method has id ``3.6``.

        :param OcaProtoONo ProtoObjectNumber: Input parameter.

    .. _ocablockfactory_getprotomembers:

    .. cpp:function:: OcaStatus GetProtoMembers(OcaList<OcaProtoObjectIdentification> &Members)

        Gets the factory's list of proto-members. Does not recurse inner
        proto-blocks. The return value indicates whether the list was
        successfully retrieved.

        This method has id ``3.7``.

        :param OcaList<OcaProtoObjectIdentification> Members: Output parameter.

    .. _ocablockfactory_defineprotosignalpath:

    .. cpp:function:: OcaStatus DefineProtoSignalPath(OcaProtoSignalPath Path, OcaUint16 &Index)

        Defines a proto-signal path in the factory. The return value indicates
        whether the proto-signal path was successfully defined.

        This method has id ``3.8``.

        :param OcaProtoSignalPath Path: Input parameter.
        :param OcaUint16 Index: Output parameter.

    .. _ocablockfactory_undefineprotosignalpath:

    .. cpp:function:: OcaStatus UndefineProtoSignalPath(OcaUint16 &Index)

        Deletes a proto-signal path from the factory. The return value
        indicates whether the signal path was successfully added.

        This method has id ``3.9``.

        :param OcaUint16 Index: Output parameter.

    .. _ocablockfactory_getprotosignalpaths:

    .. cpp:function:: OcaStatus GetProtoSignalPaths(OcaMap<OcaUint16, OcaProtoSignalPath> &Members)

        Gets the factory's list of proto-signal paths. Map key is proto-signal
        path ID. Does not recurse inner proto-blocks. The return value
        indicates whether the list was successfully retrieved.

        This method has id ``3.10``.

        :param OcaMap<OcaUint16, OcaProtoSignalPath> Members: Output parameter.

    .. _ocablockfactory_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the global type identifier for blocks created by this factory.
        The return value indicates whether the identifier was successfully
        retrieved. **Added in version 2 of this class.**

        This method has id ``3.11``.

        :param OcaGlobalTypeIdentifier GlobalType: Output parameter.

    .. _ocablockfactory_setglobaltype:

    .. cpp:function:: OcaStatus SetGlobalType(OcaGlobalTypeIdentifier GlobalType)

        Sets the global type identifier for blocks created by this factory.
        The return value indicates whether the identifier was successfully
        set. **Added in version 2 of this class.**

        This method has id ``3.12``.

        :param OcaGlobalTypeIdentifier GlobalType: Input parameter.


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
    
    
