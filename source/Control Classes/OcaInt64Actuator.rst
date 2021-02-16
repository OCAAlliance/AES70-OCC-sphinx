.. _ocaint64actuator:

1.1.1.1.5  OcaInt64Actuator
===========================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaInt64Actuator: OcaBasicActuator

    Basic int64 actuator.

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

    .. cpp:member:: OcaInt64 Setting

        This property has id ``5.1``.

        Int64 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaInt64 &Setting, OcaInt64 &minSetting, OcaInt64 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt64 Setting: Output parameter.
        :param OcaInt64 minSetting: Output parameter.
        :param OcaInt64 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaInt64 Value)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaInt64 Value: Input parameter.

