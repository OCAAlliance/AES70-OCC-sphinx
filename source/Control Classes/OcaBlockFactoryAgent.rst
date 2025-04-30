.. _ocablockfactoryagent:

1.2.21  OcaBlockFactoryAgent
============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaBlockFactoryAgent <ocablockfactoryagent>`

.. cpp:class:: OcaBlockFactoryAgent: OcaAgent

    Create custom **OcaBlock** instances (*blocks*). Usable only in
    reconfigurable devices. See [AES70-1](Constructing and deleting objects)]
    for an overview.

    **Properties**:


    .. _ocablockfactoryagent_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.21"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocablockfactoryagent_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocablockfactoryagent_globaltype:

    .. cpp:member:: OcaGlobalTypeIdentifier GlobalType

        Global block type identifier for reusable blocks. Blocks created by this
        Factory shall be given this value.

        This property has id ``3.1``.

    .. _ocablockfactoryagent_protoactionobjects:

    .. cpp:member:: OcaList<OcaProtoObjectIdentification> ProtoActionObjects

        List of Prototype Object Identifiers of Action Objects in the Block.

        This property has id ``3.2``.

    .. _ocablockfactoryagent_protoblockportclockmap:

    .. cpp:member:: OcaMap<OcaPortID, OcaProtoPortClockMapEntry> ProtoBlockPortClockMap

        Prototype Block Port Clock Map. This map defines the Block Port Clock
        Map that each Block constructed by this Factory shall have.

        This property has id ``3.5``.

    .. _ocablockfactoryagent_protoblockports:

    .. cpp:member:: OcaList<OcaProtoPort> ProtoBlockPorts

        List of Prototype Block Ports. This list defines the Block Ports that
        each Block constructed by this Factory shall have.

        This property has id ``3.4``.

    .. _ocablockfactoryagent_protodatasetobjects:

    .. cpp:member:: OcaList<OcaProtoObjectIdentification> ProtoDatasetObjects

        List of Prototype Object Identifiers of Dataset Objects in the Block.

        This property has id ``3.3``.

    .. _ocablockfactoryagent_protosignalpaths:

    .. cpp:member:: OcaMap<OcaID16, OcaProtoSignalPath> ProtoSignalPaths

        List of Prototype Signal Paths in the Block.

        This property has id ``3.6``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocablockfactoryagent_getglobaltype:

    .. cpp:function:: OcaStatus GetGlobalType(OcaGlobalTypeIdentifier &GlobalType)

        Gets the global type identifier for blocks created by this factory.

        This method has id ``3.1``.

        - :cpp:expr:`GlobalType`: Output parameter.


    .. _ocablockfactoryagent_setglobaltype:

    .. cpp:function:: OcaStatus SetGlobalType(OcaGlobalTypeIdentifier GlobalType)

        Sets the global type identifier for blocks created by this factory.

        This method has id ``3.2``.

        - :cpp:expr:`GlobalType`: Input parameter.


    .. _ocablockfactoryagent_addprotoactionobject:

    .. cpp:function:: OcaStatus AddProtoActionObject(OcaClassID ClassIdentification, OcaList<OcaConstructionParameter> ConstructionParameters, OcaProtoONo &ProtoObjectNumber)

        Adds a Prototype Action Object of the given class to this Factory. The
        most current version of the given class shall be used.

        This method has id ``3.3``.

        - :cpp:expr:`ClassIdentification`: Input parameter.


        - :cpp:expr:`ConstructionParameters`: Input parameter.


        - :cpp:expr:`ProtoObjectNumber`: Output parameter.


    .. _ocablockfactoryagent_addprotoblockusingfactory:

    .. cpp:function:: OcaStatus AddProtoBlockUsingFactory(OcaONo FactoryONo, OcaProtoONo &ProtoObjectNumber)

        Adds a Prototype nested Block to this Factory. When this Factory
        constructs a Block, the nested Block will be constructed as well.

        This method has id ``3.4``.

        - :cpp:expr:`FactoryONo`: Input parameter.


        - :cpp:expr:`ProtoObjectNumber`: Output parameter.


    .. _ocablockfactoryagent_getprotoactionobjects:

    .. cpp:function:: OcaStatus GetProtoActionObjects(OcaList<OcaProtoObjectIdentification> &Objects)

        Gets the Factory's list of Prototype Action Objects. Does not recurse
        nested Prototype Blocks, if any.

        This method has id ``3.5``.

        - :cpp:expr:`Objects`: Output parameter.


    .. _ocablockfactoryagent_addprotodatasetobject:

    .. cpp:function:: OcaStatus AddProtoDatasetObject(OcaClassID ClassIdentification, OcaList<OcaConstructionParameter> ConstructionParameters, OcaProtoONo &ProtoObjectNumber)

        Adds a Prototype Dataset Object of the given class to this Factory. The
        most current version of the class shall be used.

        This method has id ``3.6``.

        - :cpp:expr:`ClassIdentification`: Input parameter.


        - :cpp:expr:`ConstructionParameters`: Input parameter.


        - :cpp:expr:`ProtoObjectNumber`: Output parameter.


    .. _ocablockfactoryagent_getprotodatasetobjects:

    .. cpp:function:: OcaStatus GetProtoDatasetObjects(OcaList<OcaProtoObjectIdentification> &Datasets)

        Gets the Factory's list of Prototype Dataset Objects. Does not recurse
        nested Prototype Blocks.

        This method has id ``3.7``.

        - :cpp:expr:`Datasets`: Output parameter.


    .. _ocablockfactoryagent_deleteprotomember:

    .. cpp:function:: OcaStatus DeleteProtoMember(OcaProtoONo ProtoObjectNumber)

        Deletes a Prototype Action Object or Prototype Dataset Object from the
        Factory. If the object being deleted is an Action Object, all Prototype
        Signal Paths attached to it

        This method has id ``3.8``.

        - :cpp:expr:`ProtoObjectNumber`: Input parameter.


    .. _ocablockfactoryagent_getprotoblockports:

    .. cpp:function:: OcaStatus GetProtoBlockPorts(OcaList<OcaProtoPort> &Ports)

        Gets the Factory's list of Prototype Block Ports.

        This method has id ``3.9``.

        - :cpp:expr:`Ports`: Output parameter.


    .. _ocablockfactoryagent_setprotoblockports:

    .. cpp:function:: OcaStatus SetProtoBlockPorts(OcaList<OcaProtoPort> Ports)

        Sets the complete list of Prototype Block Ports. When the Factory
        constructs a Block, it will create a Block Port in the Block for each
        Prototype Block Port . Null list removes all Prototype Block Ports.

        This method has id ``3.10``.

        - :cpp:expr:`Ports`: Input parameter.


    .. _ocablockfactoryagent_setprotoblockport:

    .. cpp:function:: OcaStatus SetProtoBlockPort(OcaString Name, OcaIODirection PortMode, OcaPortID &ID)

        Adds a single Prototype Block Port to the factory. If the identified
        Prototype Block Port already exists in the Factory, it is replaced with
        the one from this call.

        This method has id ``3.11``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`PortMode`: Input parameter.


        - :cpp:expr:`ID`: Output parameter.


    .. _ocablockfactoryagent_deleteprotoblockport:

    .. cpp:function:: OcaStatus DeleteProtoBlockPort(OcaPortID ProtoPortID)

        If the method succeeds, deletes the designated Prototype Block Port from
        the Factory.

        This method has id ``3.12``.

        - :cpp:expr:`ProtoPortID`: Input parameter.


    .. _ocablockfactoryagent_getprotosignalpaths:

    .. cpp:function:: OcaStatus GetProtoSignalPaths(OcaMap<OcaUint16, OcaProtoSignalPath> &SignalPaths)

        Gets the Factory's list of Prototype Signal Paths. Map key is Prototype
        Signal Path ID.

        This method has id ``3.13``.

        - :cpp:expr:`SignalPaths`: Output parameter.


    .. _ocablockfactoryagent_setprotosignalpaths:

    .. cpp:function:: OcaStatus SetProtoSignalPaths(OcaMap<OcaUint16, OcaProtoSignalPath> SignalPaths)

        Gets the Factory's list of Prototype Signal Paths. Map key is Prototype
        Signal Path ID.

        This method has id ``3.14``.

        - :cpp:expr:`SignalPaths`: Input parameter.


    .. _ocablockfactoryagent_setprotosignalpath:

    .. cpp:function:: OcaStatus SetProtoSignalPath(OcaProtoSignalPath Path, OcaUint16 &Index)

        Adds or replaces a Prototype Signal Path in the Factory.

        This method has id ``3.15``.

        - :cpp:expr:`Path`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


    .. _ocablockfactoryagent_deleteprotosignalpath:

    .. cpp:function:: OcaStatus DeleteProtoSignalPath(OcaUint16 &Index)

        Deletes a Prototype Signal Path from the Factory.

        This method has id ``3.16``.

        - :cpp:expr:`Index`: Output parameter.


    .. _ocablockfactoryagent_getprotoblockportclockmap:

    .. cpp:function:: OcaStatus GetProtoBlockPortClockMap(OcaMap<OcaPortID, OcaProtoPortClockMapEntry> &Map)

        Gets the Prototype Block Port Clock Map.

        This method has id ``3.17``.

        - :cpp:expr:`Map`: Output parameter.


    .. _ocablockfactoryagent_setprotoblockportclockmap:

    .. cpp:function:: OcaStatus SetProtoBlockPortClockMap(OcaMap<OcaPortID, OcaProtoPortClockMapEntry> Map)

        Sets the complete Prototype Block Port Clock Map. Null parameter clears
        the map.

        This method has id ``3.18``.

        - :cpp:expr:`Map`: Input parameter.


    .. _ocablockfactoryagent_setprotoblockportclockmapentry:

    .. cpp:function:: OcaStatus SetProtoBlockPortClockMapEntry(OcaPortID Port, OcaProtoPortClockMapEntry MapEntry)

        Adds or replaces an entry to the Factory's current Prototype Block Port
        Clock Map

        This method has id ``3.19``.

        - :cpp:expr:`Port`: Input parameter.


        - :cpp:expr:`MapEntry`: Input parameter.


    .. _ocablockfactoryagent_deleteprotoblockportclockmapentry:

    .. cpp:function:: OcaStatus DeleteProtoBlockPortClockMapEntry(OcaPortID PortID)

        Deletes an entry from the Prototype Block Port Clock Map.

        This method has id ``3.20``.

        - :cpp:expr:`PortID`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaAgent::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

