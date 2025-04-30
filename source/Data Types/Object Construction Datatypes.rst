*****************************
Object Construction Datatypes
*****************************

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
    prototype object's class identification.

    .. cpp:member:: OcaProtoONo POno

        Prototype object number of referenced prototype object.

    .. cpp:member:: OcaClassIdentification ClassIdentification

        Class identification of referenced object.

.. _OcaProtoPort:

OcaProtoPort
============

.. cpp:struct:: OcaProtoPort


    .. cpp:member:: OcaProtoONo Owner

        Prototype object number of the prototype member that owns the prototype
        port. The value of 0 (zero) is special, and refers to the block itself,
        rather than to any of its members.

    .. cpp:member:: OcaPortID ProtoID

        ID of the prototype port.

    .. cpp:member:: OcaString Name

        Name of the prototype port.

.. _OcaProtoPortClockMapEntry:

OcaProtoPortClockMapEntry
=========================

.. cpp:struct:: OcaProtoPortClockMapEntry

    Entry describing the clocking and sampling rate conversion (if any) of an
    **OcaPort**. Stored in the **ProtoPortClockMap** property of
    **OcaBlockFactoryAgent**.

    .. cpp:member:: OcaVariant<OcaProtoONo, OcaONo> ClockONo

        Object number of the **OcaMediaClock3** object that clocks this Port.
        Value is either a prototype ONo or a regular ONo.

    .. cpp:member:: OcaSamplingRateConverterType SRCType

        Sampling rate converter type - none, asynchronous, synchronous.

.. _OcaProtoSignalPath:

OcaProtoSignalPath
==================

.. cpp:struct:: OcaProtoSignalPath

    Prototype signal path between two prototype member ports in a factory.

    .. cpp:member:: OcaProtoPort OutputProtoPort

        Output port (i.e. signal source) of the prototype signal path.

    .. cpp:member:: OcaProtoPort InputProtoPort

        Input prototype port (i.e. signal destination port) of the prototype
        signal path.

.. _OcaConstructionParameter:

OcaConstructionParameter
========================

.. cpp:struct:: OcaConstructionParameter

    Construction parameter. Defines the value of a property that will be set at
    object construction time.

    .. cpp:member:: OcaPropertyID ID

        Property ID.

    .. cpp:member:: OcaBlob Value

        Property value.

