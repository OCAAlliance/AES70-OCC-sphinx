.. _ocauint64actuator:

1.1.1.1.9  OcaUint64Actuator
============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaUint64Actuator: OcaBasicActuator

    Basic Uint64 actuator.

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

    .. cpp:member:: OcaUint64 Setting

        This property has id ``5.0``.

        Uint64 setting.

    .. cpp:function:: OcaStatus GetSetting(OcaUint64 &Setting, OcaUint64 &minSetting, OcaUint64 &maxSetting)

        This method has id ``5.1``.

        Gets the value and limits of the Gain property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaUint64 Setting: Output parameter.
        :param OcaUint64 minSetting: Output parameter.
        :param OcaUint64 maxSetting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaUint64 Setting)

        This method has id ``5.2``.

        Sets the value of the Level property. The return value indicates
        whether the property was successfully set.

        :param OcaUint64 Setting: Input parameter.

