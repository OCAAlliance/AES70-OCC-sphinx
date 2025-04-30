**************************
Block and Matrix Datatypes
**************************

.. _OcaBlockMember:

OcaBlockMember
==============

.. cpp:struct:: OcaBlockMember

    Describes an object that is a member of a block.

    .. cpp:member:: OcaObjectIdentification MemberObjectIdentification

        Object identification of a block member.

    .. cpp:member:: OcaONo ContainerObjectNumber

        Object number of a the block that contains the member.

.. _OcaPort:

OcaPort
=======

.. cpp:struct:: OcaPort

    Representation of an OCA (input or output) port that is used in the signal
    path representation of an OCA device.

    .. cpp:member:: OcaONo Owner

        Object number of the object that owns the port.

    .. cpp:member:: OcaPortID ID

        ID of the port.

    .. cpp:member:: OcaString Name

        Port ID of the port.

.. _OcaPortMode:

OcaPortMode
===========

.. cpp:enum:: OcaPortMode : uint8_t

    Enum that describes whether a port is for input or output.

    .. cpp:enumerator:: Input = 1

        Input port

    .. cpp:enumerator:: Output = 2

        Output port

.. _OcaPortID:

OcaPortID
=========

.. cpp:struct:: OcaPortID

    Unique identifier of input or output port within a given worker or block
    class. Port numbers are ordinals starting at 1, and there are separate
    numbering spaces for input and output ports.

    .. cpp:member:: OcaPortMode Mode

        Enum that indicates whether the port is for input or output.

    .. cpp:member:: OcaUint16 Index

        Index of port within given input or output set of specified object.

.. _OcaSignalPath:

OcaSignalPath
=============

.. cpp:struct:: OcaSignalPath

    Signal path between two object ports in the same device.

    .. cpp:member:: OcaPort SourcePort

        Source port (i.e. output port) of the signal path.

    .. cpp:member:: OcaPort SinkPort

        Sink port (i.e. input port) of the signal path.

.. _OcaProtoMember:

OcaProtoMember
==============

.. cpp:type:: OcaProtoMember = OcaProtoONo

    Describes proto-member of a block factory

.. _OcaProtoONo:

OcaProtoONo
===========

.. cpp:type:: OcaProtoONo = OcaUint32

    Object number of an OCA object.

.. _OcaProtoObjectIdentification:

OcaProtoObjectIdentification
============================

.. cpp:struct:: OcaProtoObjectIdentification

    Prototype object identification. Composite of prototype object number and
    prototype object's class identification. Used in **OcaBlockFactory**.

    .. cpp:member:: OcaProtoONo POno

        Prototype object number of referenced prototype object.

    .. cpp:member:: OcaClassIdentification ClassIdentification

        Class identification of referenced object.

.. _OcaProtoPortID:

OcaProtoPortID
==============

.. cpp:struct:: OcaProtoPortID

    Unique identifier of prototype input or output port within a block factory.
    Prototype port numbers are ordinals starting at 1, and there are separate
    numbering spaces for input and output ports.

    .. cpp:member:: OcaPortMode Mode

        Enum that indicates whether the prototype port is an for input or
        output.

    .. cpp:member:: OcaUint16 Index

        Number of the proto port within input or output group. 1-based.

.. _OcaProtoPort:

OcaProtoPort
============

.. cpp:struct:: OcaProtoPort

    Representation of an OCA (input or output) proto-port that is used in the
    proto-signal path representation of an OCA device.

    .. cpp:member:: OcaProtoONo Owner

        Proto-object number of the proto-member that owns the proto-port. **The
        value of 0 (zero) is special, and refers to the block itself, rather
        than to any of its members.**

    .. cpp:member:: OcaProtoPortID ProtoID

        ID of the proto-port.

    .. cpp:member:: OcaString Name

        Name of the proto-port.

.. _OcaProtoSignalPath:

OcaProtoSignalPath
==================

.. cpp:struct:: OcaProtoSignalPath

    Proto-signal path between two proto-member ports in a factory.

    .. cpp:member:: OcaProtoPort SourceProtoPort

        Source proto-port (i.e. output port) of the proto-signal path.

    .. cpp:member:: OcaProtoPort SinkProtoPort

        Sink proto-port (i.e. input port) of the proto-signal path.

.. _OcaMatrixCoordinate:

OcaMatrixCoordinate
===================

.. cpp:type:: OcaMatrixCoordinate = OcaUint16

    Coordinate value (x or y) for **OcaMatrix. ** Value is zero-relative, i.e.
    the first row or column is number zero. A value of 65535 means all rows or
    columns.

.. _OcaObjectSearchResult:

OcaObjectSearchResult
=====================

.. cpp:struct:: OcaObjectSearchResult

    Result of object search via the Find...() methods of **OcaBlock**. Dynamic
    format, form used depends on type of search and options. The FieldMap
    parameter of the Find...() methods specifies which optional fields should be
    returned as nonnull.

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

    Bitset that describes the contents of an **OcaSearchResult**

