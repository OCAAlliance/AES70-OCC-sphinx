.. _ocafloat32actuator:

1.1.1.1.10  OcaFloat32Actuator
==============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaFloat32Actuator: OcaBasicActuator

    Basic float32 actuator.

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

    .. cpp:member:: OcaFloat32 Setting

        This property has id ``5.0``.

        Float32 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaFloat32 &Setting, OcaFloat32 &minSetting, OcaFloat32 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the **Setting** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaFloat32 Setting: Output parameter.
        :param OcaFloat32 minSetting: Output parameter.
        :param OcaFloat32 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaFloat32 Setting)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaFloat32 Setting: Input parameter.

