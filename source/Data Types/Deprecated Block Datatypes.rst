**************************
Deprecated Block Datatypes
**************************

.. _OcaProtoMember:

OcaProtoMember
==============

.. cpp:struct:: OcaProtoMember

    Describes proto-member of a block factory. Deprecated in v3.

    .. cpp:member:: OcaProtoONo ProtoMemberPOno

        Describes prototype of member

.. _OcaObjectSearchResult:

OcaObjectSearchResult
=====================

.. cpp:struct:: OcaObjectSearchResult

    Result of object search via the Find...() methods of **OcaBlock**. Dynamic
    format, form used depends on type of search and options. The **FieldMap**
    parameter of the Find...() methods specifies which optional fields should be
    returned as nonnull. D**eprecated** in OCA 1.5, replaced by
    **OcaMemberSearchResult.**

    .. cpp:member:: OcaONo ONo

        ONo of object found

    .. cpp:member:: OcaClassIdentification ClassIdentification

        Class identification (class ID + class version) of object found

    .. cpp:member:: OcaONoPath ContainerPath

        Chain of ONos leading from root to this object's container

    .. cpp:member:: OcaString Role

        Object role in device

    .. cpp:member:: OcaString Label

        Object user-specified label

.. _OcaObjectSearchResultFlags:

OcaObjectSearchResultFlags
==========================

.. cpp:type:: OcaObjectSearchResultFlags = OcaBitSet16

    Bitset that describes the contents of an **OcaObjectSearchResult.** In OCA
    1.5, replaced by** OcaActionObjectSearchResultFlags.**

.. _OcaOPath:

OcaOPath
========

.. cpp:struct:: OcaOPath

    Object address. Composite of network address in which object resides, and
    object number.

    .. cpp:member:: OcaNetworkHostID HostID

        Service ID of host that contains the referenced object, as registered in
        the network discovery system being used. Format depends on discovery
        system type. NOTE For AES70-2023 and later, the value for this property
        will normally be the Service Name of the target host's service, as
        registered in DNS-SD - see [AES70-3]. For AES70-2018, the value for this
        property will normally be the value of the **ServiceID** property of the
        **OcaControlNetwork** object that describes the target host's network
        connection. This property is inherited from **OcaApplicationNetwork**.

    .. cpp:member:: OcaONo ONo

        Object number of referenced object.

