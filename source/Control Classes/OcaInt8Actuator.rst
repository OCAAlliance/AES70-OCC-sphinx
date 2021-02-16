.. _ocaint8actuator:

1.1.1.1.2  OcaInt8Actuator
==========================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaInt8Actuator: OcaBasicActuator

    Basic int8 actuator.

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

    .. cpp:member:: OcaInt8 Setting

        This property has id ``5.1``.

        Int8 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaInt8 &Setting, OcaInt8 &minSetting, OcaInt8 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt8 Setting: Output parameter.
        :param OcaInt8 minSetting: Output parameter.
        :param OcaInt8 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaInt8 Setting)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaInt8 Setting: Input parameter.

