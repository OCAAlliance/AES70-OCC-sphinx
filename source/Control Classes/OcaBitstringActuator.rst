.. _ocabitstringactuator:

1.1.1.1.13  OcaBitstringActuator
================================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaBitstringActuator: OcaBasicActuator

    Bitstring actuator. Maximum bitstring length is 65,536 bits.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``5.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``5.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaBitstring Bitstring

        This property has id ``5.0``.

        The bitstring data.

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &nrBits)

        This method has id ``5.1``.

        Gets the number of bits in the string. The return value indicates
        whether the property was successfully gathered.

        :param OcaUint16 nrBits: Output parameter.

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaBoolean &Value)

        This method has id ``5.2``.

        Gets the bit value of the given bit. The return value indicates
        whether the property was successfully gathered.

        :param OcaUint16 bitNr: Input parameter.
        :param OcaBoolean Value: Output parameter.

    .. cpp:function:: OcaStatus SetBit(OcaUint16 bitNr, OcaBoolean Value)

        This method has id ``5.3``.

        Sets the bit value of the given bit. The return value indicates
        whether the property was successfully set.

        :param OcaUint16 bitNr: Input parameter.
        :param OcaBoolean Value: Input parameter.

    .. cpp:function:: OcaStatus GetBitstring(OcaBitstring &BitString)

        This method has id ``5.4``.

        Gets the entire bitstring.The return value indicates whether the
        property was successfully gathered.

        :param OcaBitstring BitString: Output parameter.

    .. cpp:function:: OcaStatus SetBitstring(OcaBitstring BitString)

        This method has id ``5.5``.

        Sets the entire bitstring. The return value indicates whether the
        property was successfully set.

        :param OcaBitstring BitString: Input parameter.

