**************
Port Datatypes
**************

.. _OcaPortID:

OcaPortID
=========

.. cpp:struct:: OcaPortID

    Unique identifier of input or output Port within a given Worker or Block
    class. Port numbers are ordinals starting at 1, and there are separate
    numbering spaces for input and output Ports.

    .. cpp:member:: OcaIODirection Direction

        Indicates whether the port is for input or output. Before OCA 1.5, was
        named **Mode**, with (now-renamed) datatype **OcaPortMode.**

    .. cpp:member:: OcaUint16 Index

        Index of port within given input or output set of specified object.

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

    .. cpp:member:: OcaString Role

        Role of the port in the containing object. Values beginning with "oca"
        in any character case are reserved for AES use.

.. _OcaPortClockMapEntry:

OcaPortClockMapEntry
====================

.. cpp:struct:: OcaPortClockMapEntry

    Port clock map entry that describes the clocking and sample-rate conversion
    (if any) of an **OcaPort**.

    .. cpp:member:: OcaONo ClockONo

        Object number of the **OcaMediaClock3** object that clocks this port.

    .. cpp:member:: OcaSamplingRateConverterType SRCType

        Sampling Rate Converter (SRC) type - none, asynchronous, synchronous.

.. _OcaPortIdentification:

OcaPortIdentification
=====================

.. cpp:struct:: OcaPortIdentification

    Representation of an OCA (input or output) port that is used in the signal
    path representation of an OCA device.

    .. cpp:member:: OcaONo Owner

        ONo of object that owns the port.

    .. cpp:member:: OcaPortID ID

        ID of the port. ID={mode,index}; mode is input or output.

