.. _ocablockfactory:

1.1.4  OcaBlockFactory
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaBlockFactory <ocablockfactory>`

.. cpp:class:: OcaBlockFactory: OcaWorker

    Factory to create custom block instances. Used only in reconfigurable
    devices. The idea is that you instantiate a factory once, populate it with
    proto-objects and proto-signal paths, then use it subsequently to
    instantiate identical blocks. In this context, **proto-object** means a
    prototype of a block member. Unbound objects are identified by
    **proto-object numbers (PONo's)** instead of actual object numbers. PONos
    are unique within the factory, and are converted to globally unique object
    numbers ONos) in all new block instances that the factory builds.
    Correspondingly, **proto-signal path** means a signal path expressed in
    terms of **PONos** rather than **ONos**. When the factory constructs a
    block, it converts all of its unbound signal paths to normal (bound) signal
    paths by mapping its **PONos** into **ONos**. The factory also holds a list
    of **proto-blockports** which are **OcaPorts** that are allocated to new
    blocks the factory builds. As well, the proto-objects in the factory may
    contain lists of their own proto-ports. Together, the factory's proto-ports
    and its members' proto-ports are used to define the factory's set of
    proto-signal paths. Factories may be predefined at time of device
    manufacture, or constructed "on the fly" by controllers. To **create a
    factory**, the controller calls a block's **CreateMember(...)** method with
    the **ClassID** of this class (**OcaBlockFactory**). Factories ignore which
    block creates them, so it makes no difference which block's
    **CreateMember(...)** method is used. It will usually make the most sense to
    use the Root Block's method. To add proto-objects, proto-ports, and
    proto-signal paths to a block factory, the controller calls the factory's
    **DefineProtoMember(...), DefineProtoPort(...), and
    DefineProtoSignalPath(...**) methods, respectively.

    **Properties**:


    .. _ocablockfactory_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.4"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocablockfactory_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2


        This property has id ``1.2``.

    .. _ocablockfactory_protoports:

    .. cpp:member:: OcaList<OcaProtoPort> ProtoPorts

        List of proto-ports for built objects. The factory itself has no ports.

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


    .. _ocablockfactory_defineprotoport:

    .. cpp:function:: OcaStatus DefineProtoPort(OcaString name, OcaPortMode portmode, OcaProtoPortID &id)

        Defines a proto-port in the factory. If proto-port already exists, it is
        replaced with the one from this call. The return value indicates whether
        the proto-port was successfully added.

        This method has id ``3.1``.

        - :cpp:expr:`name`: Input parameter.


        - :cpp:expr:`portmode`: Input parameter.


        - :cpp:expr:`id`: Output parameter.


    .. _ocablockfactory_undefineprotoport:

    .. cpp:function:: OcaStatus UndefineProtoPort(OcaProtoPortID ProtoPortID)

        Deletes a proto-port from the factory. The return value indicates
        whether the proto-port was successfully deleted.

        This method has id ``3.2``.

        - :cpp:expr:`ProtoPortID`: Input parameter.


    .. _ocablockfactory_getprotoports:

    .. cpp:function:: OcaStatus GetProtoPorts(OcaList<OcaProtoPort> &Ports)

        Gets the factory's list of proto-ports. The return value indicates
        whether the list was successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`Ports`: Output parameter.


    .. _ocablockfactory_defineprotomember:

    .. cpp:function:: OcaStatus DefineProtoMember(OcaClassID ClassIdentification, variant ConstructionParameters, OcaProtoONo &ProtoObjectNumber)

        Defines a proto-member of the given class in the factory. The most
        current version of the class is used. The return value indicates whether
        the proto-member was successfully defined.

        This method has id ``3.4``.

        - :cpp:expr:`ClassIdentification`: Input parameter.


        - :cpp:expr:`ConstructionParameters`: Input parameter.


        - :cpp:expr:`ProtoObjectNumber`: Output parameter.


    .. _ocablockfactory_defineprotomemberusingfactory:

    .. cpp:function:: OcaStatus DefineProtoMemberUsingFactory(OcaONo FactoryONo, OcaProtoONo &ProtoObjectNumber)

        Defines a proto-member which will be instantiated by a specified factory
        when the block is built. The return value indicates whether the
        proto-member was successfully defined.

        This method has id ``3.5``.

        - :cpp:expr:`FactoryONo`: Input parameter.


        - :cpp:expr:`ProtoObjectNumber`: Output parameter.


    .. _ocablockfactory_undefineprotomember:

    .. cpp:function:: OcaStatus UndefineProtoMember(OcaProtoONo ProtoObjectNumber)

        Deletes a proto-member from the factory. Deletes all proto-signal paths
        attached to its ports. The return value indicates whether the member was
        successfully deleted.

        This method has id ``3.6``.

        - :cpp:expr:`ProtoObjectNumber`: Input parameter.


    .. _ocablockfactory_getprotomembers:

    .. cpp:function:: OcaStatus GetProtoMembers(OcaList<OcaProtoObjectIdentification> &Members)

        Gets the factory's list of proto-members. Does not recurse inner
        proto-blocks. The return value indicates whether the list was
        successfully retrieved.

        This method has id ``3.7``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablockfactory_defineprotosignalpath:

    .. cpp:function:: OcaStatus DefineProtoSignalPath(OcaProtoSignalPath Path, OcaUint16 &Index)

        Defines a proto-signal path in the factory. The return value indicates
        whether the proto-signal path was successfully defined.

        This method has id ``3.8``.

        - :cpp:expr:`Path`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


    .. _ocablockfactory_undefineprotosignalpath:

    .. cpp:function:: OcaStatus UndefineProtoSignalPath(OcaUint16 &Index)

        Deletes a proto-signal path from the factory. The return value indicates
        whether the signal path was successfully added.

        This method has id ``3.9``.

        - :cpp:expr:`Index`: Output parameter.


    .. _ocablockfactory_getprotosignalpaths:

    .. cpp:function:: OcaStatus GetProtoSignalPaths(OcaMap<OcaUint16, OcaProtoSignalPath> &Members)

        Gets the factory's list of proto-signal paths. Map key is proto-signal
        path ID. Does not recurse inner proto-blocks. The return value indicates
        whether the list was successfully retrieved.

        This method has id ``3.10``.

        - :cpp:expr:`Members`: Output parameter.


    .. _ocablockfactory_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the global type identifier for blocks created by this factory. The
        return value indicates whether the identifier was successfully
        retrieved. **Added in version 2 of this class.**

        This method has id ``3.11``.

        - :cpp:expr:`GlobalType`: Output parameter.


    .. _ocablockfactory_setglobaltype:

    .. cpp:function:: OcaStatus SetGlobalType(OcaGlobalTypeIdentifier GlobalType)

        Sets the global type identifier for blocks created by this factory. The
        return value indicates whether the identifier was successfully set.
        **Added in version 2 of this class.**

        This method has id ``3.12``.

        - :cpp:expr:`GlobalType`: Input parameter.


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

