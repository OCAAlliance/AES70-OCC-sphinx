.. _ocatemperaturesensor:

1.1.2.5  OcaTemperatureSensor
=============================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaTemperatureSensor: OcaSensor

    Basic temperature sensor.

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

    .. cpp:member:: OcaTemperature Reading

        This property has id ``4.1``.

        Temperature value (Celsius).

    .. cpp:function:: OcaStatus GetReading(OcaTemperature &Reading, OcaTemperature &minReading, OcaTemperature &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaTemperature Reading: Output parameter.
        :param OcaTemperature minReading: Output parameter.
        :param OcaTemperature maxReading: Output parameter.

