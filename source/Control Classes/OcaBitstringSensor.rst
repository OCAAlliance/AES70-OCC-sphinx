.. _ocabitstringsensor:

1.1.2.1.13  OcaBitstringSensor
==============================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaBitstringSensor: OcaBasicSensor

    Bit string sensor.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``5.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``5.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaBitstring BitString

        This property has id ``5.1``.

        The bitstring.

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &NrBits)

        This method has id ``5.1``.

        Gets the number of bits of the bitmask data. Returned status indicates
        success or failure of the retrieval.

        :param OcaUint16 NrBits: Output parameter.

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaUint8 &bit)

        This method has id ``5.2``.

        Gets the value of the given bit. Return status indicates success or
        failure of the retrieval.

        :param OcaUint16 bitNr: Input parameter.
        :param OcaUint8 bit: Output parameter.

    .. cpp:function:: OcaStatus GetBitString(OcaBitstring &BitString)

        This method has id ``5.3``.

        Gets the entire bitstring. Return status indicates success or failure
        of the retrieval.

        :param OcaBitstring BitString: Output parameter.

