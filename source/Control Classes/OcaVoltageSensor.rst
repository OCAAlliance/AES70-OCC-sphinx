.. _ocavoltagesensor:

1.1.2.7  OcaVoltageSensor
=========================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaVoltageSensor: OcaSensor

    Basic voltage sensor.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaVoltage Reading

        This property has id ``4.0``.

        Voltage value (volts).

    .. cpp:function:: OcaStatus GetReading(OcaVoltage &Reading, OcaVoltage &minReading, OcaVoltage &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaVoltage Reading: Output parameter.
        :param OcaVoltage minReading: Output parameter.
        :param OcaVoltage maxReading: Output parameter.

