.. _ocastringactuator:

1.1.1.1.12  OcaStringActuator
=============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaStringActuator: OcaBasicActuator

    String actuator.

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

    .. cpp:member:: OcaString Setting

        This property has id ``5.1``.

        Value.

    .. cpp:member:: OcaUint16 MaxLen

        This property has id ``5.2``.

        Maximum string length that this object can accept.

    .. cpp:function:: OcaStatus GetSetting(OcaString &Value)

        This method has id ``5.1``.

        Gets the value and max length of the Value property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaString Value: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaString Value)

        This method has id ``5.2``.

        Sets the value of the Value property. The return value indicates
        whether the property was successfully set.

        :param OcaString Value: Input parameter.

    .. cpp:function:: OcaStatus GetMaxLen(OcaUint16 &Len)

        This method has id ``5.3``.

        Gets the maximum string length that this object can handle.

        :param OcaUint16 Len: Output parameter.

