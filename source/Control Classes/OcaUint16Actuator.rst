.. _ocauint16actuator:

1.1.1.1.7  OcaUint16Actuator
============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaUint16Actuator: OcaBasicActuator

    Basic uint16 actuator.

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

    .. cpp:member:: OcaUint16 Setting

        This property has id ``5.1``.

        Uint16 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaUint16 &Setting, OcaUint16 &minSetting, OcaUint16 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the Setting property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaUint16 Setting: Output parameter.
        :param OcaUint16 minSetting: Output parameter.
        :param OcaUint16 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaUint16 Setting)

        This method has id ``5.2``.

        Sets the value of the **Setting** property. The return value indicates
        whether the property was successfully set.

        :param OcaUint16 Setting: Input parameter.

