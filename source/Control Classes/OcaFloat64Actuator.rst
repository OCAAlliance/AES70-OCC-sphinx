.. _ocafloat64actuator:

1.1.1.1.11  OcaFloat64Actuator
==============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaFloat64Actuator: OcaBasicActuator

    Basic Float64 actuator.

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

    .. cpp:member:: OcaFloat64 Setting

        This property has id ``5.0``.

        Float64 value.

    .. cpp:function:: OcaStatus GetSetting(OcaFloat64 &Setting, OcaFloat64 &minSetting, OcaFloat64 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaFloat64 Setting: Output parameter.
        :param OcaFloat64 minSetting: Output parameter.
        :param OcaFloat64 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaFloat64 Setting)

        This method has id ``5.2``.

        Sets the value of the Level property. The return value indicates
        whether the property was successfully set.

        :param OcaFloat64 Setting: Input parameter.

