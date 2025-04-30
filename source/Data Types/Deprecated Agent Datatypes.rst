**************************
Deprecated Agent Datatypes
**************************

.. _OcaProtoPortID:

OcaProtoPortID
==============

.. cpp:struct:: OcaProtoPortID

    Unique identifier of prototype input or output port within a block factory.
    Prototype port numbers are ordinals starting at 1, and there are separate
    numbering spaces for input and output ports. **Deprecated** in AES70-2022,
    replaced by **OcaPortID**, which is identical.

    .. cpp:member:: OcaIODirection Direction

        Enum that indicates whether the prototype port is an for input or
        output.

    .. cpp:member:: OcaUint16 Index

        Number of the proto port within input or output group. 1-based.

