.. _ocabooleanactuator:

1.1.1.1.1  OcaBooleanActuator
=============================

Extends :ref:`OcaBasicActuator <ocabasicactuator>`.

.. cpp:class:: OcaBooleanActuator: OcaBasicActuator

    Basic boolean actuator.

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

    .. cpp:member:: OcaBoolean Setting

        This property has id ``5.0``.

        Boolean setting.

    .. cpp:function:: OcaStatus GetSetting(OcaBoolean &Setting)

        This method has id ``5.1``.

        Gets the **Setting** property. The return value indicates whether the
        data was successfully retrieved.

        :param OcaBoolean Setting: Output parameter.

    .. cpp:function:: OcaStatus SetSetting(OcaBoolean Setting)

        This method has id ``5.2``.

        Sets the **Setting** property. The return value indicates whether the
        property was successfully set.

        :param OcaBoolean Setting: Input parameter.

