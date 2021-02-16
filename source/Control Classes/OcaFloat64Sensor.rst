.. _ocafloat64sensor:

1.1.2.1.11  OcaFloat64Sensor
============================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaFloat64Sensor: OcaBasicSensor

    Basic Float64 sensor.

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

    .. cpp:member:: OcaFloat64 Reading

        This property has id ``5.1``.

        Uint64 reading.

    .. cpp:function:: OcaStatus GetReading(OcaFloat64 &Reading, OcaFloat64 &minReading, OcaFloat64 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaFloat64 Reading: Output parameter.
        :param OcaFloat64 minReading: Output parameter.
        :param OcaFloat64 maxReading: Output parameter.

