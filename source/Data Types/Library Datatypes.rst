*****************
Library Datatypes
*****************

.. _OcaLibVolStandardTypeID:

OcaLibVolStandardTypeID
=======================

.. cpp:enum:: OcaLibVolStandardTypeID : uint8_t

    Enum that describes type of data in a standard library volume.

    .. cpp:enumerator:: None = 0

        Empty library

    .. cpp:enumerator:: ParamSet = 1

        ParamSet library

    .. cpp:enumerator:: Patch = 2

        Patch library

    .. cpp:enumerator:: Program = 3

        A program that may be run by an OcaTask

.. _OcaLibVolType:

OcaLibVolType
=============

.. cpp:struct:: OcaLibVolType

    Globally unique identifier of a library type.

    .. cpp:member:: OcaOrganizationID Authority

        Unique identifier of organization that has authority over this library
        volume type. A zero value indicates a standard library volume type
        defined by the AES70 standard.

    .. cpp:member:: OcaUint32 ID

        ID of library volume type defined by given Authority. Value is unique
        within the given Authority. If Authority=0, the values of this property
        are given by enum **OcaLibVolStandardID.**

.. _OcaLibraryIdentifier:

OcaLibraryIdentifier
====================

.. cpp:struct:: OcaLibraryIdentifier

    Full identifier (type + object number) of Library (i.e. of an **OcaLibrary**
    instance)

    .. cpp:member:: OcaLibVolType Type

        Type of the library (= type of its volumes)

    .. cpp:member:: OcaONo ONo

        Object number of library.

.. _OcaLibVolID:

OcaLibVolID
===========

.. cpp:type:: OcaLibVolID = OcaUint32

    Unique identifier of a library volume within its library.

.. _OcaLibVolIdentifier:

OcaLibVolIdentifier
===================

.. cpp:struct:: OcaLibVolIdentifier

    Unique identifier of a library volume within the device.

    .. cpp:member:: OcaONo Library

        Library that holds the LibVol in question.

    .. cpp:member:: OcaLibVolID ID

        ID of LibVol within the given library.

.. _OcaLibAccess:

OcaLibAccess
============

.. cpp:enum:: OcaLibAccess : uint8_t

    Library volume access modes

    .. cpp:enumerator:: None = 0

        The noble savage: Can't read, can't write.

    .. cpp:enumerator:: ReadOnly = 1

        Look but don't touch.

    .. cpp:enumerator:: ReadExpand = 2

        Read and add, but no replacement or deletion.

    .. cpp:enumerator:: Full = 3

        All operations allowed.

.. _OcaLibVolMetadata:

OcaLibVolMetadata
=================

.. cpp:struct:: OcaLibVolMetadata

    Descriptor of a library volume. See **03 OcaLibrary** for explanation.

    .. cpp:member:: OcaString Name

        Name of library volume

    .. cpp:member:: OcaLibVolType VolType

        Type of library volume

    .. cpp:member:: OcaLibAccess Access

        Access mode of library volume - readonly or readwrite.

    .. cpp:member:: OcaUint32 Version

        Version number of library volume.

    .. cpp:member:: OcaString Creator

        Name of creator of library volume.

    .. cpp:member:: OcaTimePTP UpDate

        Latest update timestamp.

.. _OcaLibVol:

OcaLibVol
=========

.. cpp:struct:: OcaLibVol

    Library volume. template. Template parameter is datatype of the volume. See
    **03 OcaLibrary** for explanation.

    .. cpp:member:: OcaLibVolMetadata Metadata

        Descriptor of library volume

    .. cpp:member:: OcaBlob Data

        Contents of library volume. Type depends on template parameter.

.. _OcaLibVolData_ParamSet:

OcaLibVolData_ParamSet
======================

.. cpp:struct:: OcaLibVolData_ParamSet

    Library volume data for a Parset (short for Parameter Set) volume. A Parset
    is a collection of operating parameter settings that can be applied to a
    block. Each Parset is associated with a specific block type, but not with a
    specific instance of that type. A Parset may be applied to any block
    instance of the associated type. A block's type is a the object number of
    its factory or, for factory-defined blocks, a unique identifier set at time
    of manufacture.

    .. cpp:member:: OcaONo TargetBlockType

        Block type to which this paramset applies. A block's type is a the
        object number of its factory or, for factory-defined blocks, a unique
        identifier set at time of manufacture

    .. cpp:member:: OcaBlob ParData

        ParamSet payload

.. _OcaLibParamSetAssignment:

OcaLibParamSetAssignment
========================

.. cpp:struct:: OcaLibParamSetAssignment

    A ParamSet assigment is the description of a binding of a ParamSet to a
    block instance.

    .. cpp:member:: OcaLibVolIdentifier ParamSetIdentifier

        Identifier of the library volume that holds the paramset.

    .. cpp:member:: OcaONo TargetBlockONo

        Object number of the block to which the paramset assignment applies.

.. _OcaLibVolData_Patch:

OcaLibVolData_Patch
===================

.. cpp:type:: OcaLibVolData_Patch = OcaList<OcaLibParamSetAssignment>

    Library volume data for a Patch volume. A Patch a collection of ParamSet
    assignments. A ParamSet assigment is the description of a binding of a
    ParamSet to a block instance. To "apply" a Patch is to apply all of its
    assignments. To apply an assignment is to set all of its ParamSet's
    parameter values into its block.

.. _OcaLibVolData_Program:

OcaLibVolData_Program
=====================

.. cpp:type:: OcaLibVolData_Program = OcaBlob

    Library volume data for a Program volume. A Program is an executable program
    or script that may be run by an OcaTask.

