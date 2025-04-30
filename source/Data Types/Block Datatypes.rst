***************
Block Datatypes
***************

.. _OcaBlockMember:

OcaBlockMember
==============

.. cpp:struct:: OcaBlockMember

    Describes an object that is a member of a block.

    .. cpp:member:: OcaObjectIdentification MemberObjectIdentification

        Object identification of a block member.

    .. cpp:member:: OcaONo ContainerObjectNumber

        Object number of a the block that contains the member.

.. _OcaSignalPath:

OcaSignalPath
=============

.. cpp:struct:: OcaSignalPath

    Signal path between two OcaPorts in the same device.

    .. cpp:member:: OcaPort OutputPort

        Output port. Signal originates here.

    .. cpp:member:: OcaPort InputPort

        Input port. Signal is received here.

.. _OcaActionObjectSearchResultFlags:

OcaActionObjectSearchResultFlags
================================

.. cpp:type:: OcaActionObjectSearchResultFlags = OcaBitSet16

    Bitset that specifies the fields to be returned by a search for Action
    Objects in a Block

.. _OcaActionObjectSearchResult:

OcaActionObjectSearchResult
===========================

.. cpp:struct:: OcaActionObjectSearchResult

    Result of Action Object search via the **FindActionObject...()** methods of
    **OcaBlock**. Dynamic format, form used depends on type of search and
    options.

    .. cpp:member:: OcaObjectIdentification Identification

        ONo & class identification of Action Object found

    .. cpp:member:: OcaONoPath ContainerPath

        Array of ONos leading from root to this Action Object's Owner

    .. cpp:member:: OcaString Role

        **Role** property of Action Object found

    .. cpp:member:: OcaString Label

        **Label** property of Action Object found

.. _OcaDatasetSearchResult:

OcaDatasetSearchResult
======================

.. cpp:struct:: OcaDatasetSearchResult

    Result of Dataset search via the **FindDatasets(...)** and
    **FindDatasetsRecursive(...)** methods of **OcaBlock**.

    .. cpp:member:: OcaBlockMember Object

        Member descriptor of Dataset Object

    .. cpp:member:: OcaString Name

        Dataset name

    .. cpp:member:: OcaMimeType Type

        Dataset type

.. _OcaBlockConfigurability:

OcaBlockConfigurability
=======================

.. cpp:type:: OcaBlockConfigurability = OcaBitSet16

    Bitset that defines a Block's Configurability.

.. _OcaGlobalTypeIdentifier:

OcaGlobalTypeIdentifier
=======================

.. cpp:struct:: OcaGlobalTypeIdentifier

    Globally unique identifier of something that belongs to an organization. An
    identifier with both Authority and ID fields of zero shall be interpreted as
    a null value.

    .. cpp:member:: OcaOrganizationID Organization

        Unique identifier of organization that has authority over this reusable
        block type.

    .. cpp:member:: OcaUint32 ID

        ID of item defined by given Authority. Value is unique within the given
        Authority.

