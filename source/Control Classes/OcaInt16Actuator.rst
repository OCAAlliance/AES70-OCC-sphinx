.. _ocaint16actuator:

1.1.1.1.3  OcaInt16Actuator
===========================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaInt16Actuator: OcaBasicActuator

    Basic int16 actuator.

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

    .. cpp:member:: OcaInt16 Setting

        This property has id ``5.0``.

        Int16 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaInt16 &Setting, OcaInt16 &minSetting, OcaInt16 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt16 Setting: Output parameter.
        :param OcaInt16 minSetting: Output parameter.
        :param OcaInt16 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaInt16 Setting)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaInt16 Setting: Input parameter.

