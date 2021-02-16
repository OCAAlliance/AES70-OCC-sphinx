.. _ocauint8actuator:

1.1.1.1.6  OcaUint8Actuator
===========================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaUint8Actuator: OcaBasicActuator

    Basic uint8 actuator.

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

    .. cpp:member:: OcaUint8 Setting

        This property has id ``5.0``.

        Uint8 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaUint8 &Setting, OcaUint8 &minSetting, OcaUint8 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaUint8 Setting: Output parameter.
        :param OcaUint8 minSetting: Output parameter.
        :param OcaUint8 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaUint8 Setting)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaUint8 Setting: Input parameter.

