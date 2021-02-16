.. _ocastringsensor:

1.1.2.1.12  OcaStringSensor
===========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaStringSensor: OcaBasicSensor

    Text string sensor.

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

    .. cpp:member:: OcaString String

        This property has id ``5.1``.

        The string.

    .. cpp:member:: OcaUint16 MaxLen

        This property has id ``5.2``.

        Maximum length of the returned string. May be readonly in some
        implementations.

    .. cpp:function:: OcaStatus GetString(OcaString &String)

        This method has id ``5.1``.

        Gets the entire string. Return status indicates success or failure of
        the retrieval.

        :param OcaString String: Output parameter.

    .. cpp:function:: OcaStatus GetMaxLen(OcaUint16 &maxLen)

        This method has id ``5.2``.

        Gets the maximum number of bytes that may be returned. Returned status
        indicates success or failure of the retrieval.

        :param OcaUint16 maxLen: Output parameter.

    .. cpp:function:: OcaStatus SetMaxLen(OcaUint16 maxLen)

        This method has id ``5.3``.

        Sets the maximum number of bytes that the object may return. Returned
        status indicates success or failure of the set.

        :param OcaUint16 maxLen: Input parameter.

