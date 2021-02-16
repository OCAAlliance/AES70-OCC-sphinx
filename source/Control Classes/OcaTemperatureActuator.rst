.. _ocatemperatureactuator:

1.1.1.20  OcaTemperatureActuator
================================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaTemperatureActuator: OcaActuator

    A temperature actuator. Works in Celsius.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaTemperature Temperature

        This property has id ``4.1``.

        The temperature.

    .. cpp:function:: OcaStatus GetTemperature(OcaTemperature &temperature, OcaTemperature &minTemperature, OcaTemperature &maxTemperature)

        This method has id ``4.1``.

        Gets the value of the Temperature property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaTemperature temperature: Output parameter.
        :param OcaTemperature minTemperature: Output parameter.
        :param OcaTemperature maxTemperature: Output parameter.

    .. cpp:function:: OcaStatus SetTemperature(OcaTemperature temperature)

        This method has id ``4.2``.

        Sets the value of the Temperature property. The return value indicates
        whether the property was successfully set.

        :param OcaTemperature temperature: Input parameter.

