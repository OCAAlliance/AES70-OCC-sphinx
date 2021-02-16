.. _ocaint8sensor:

1.1.2.1.2  OcaInt8Sensor
========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaInt8Sensor: OcaBasicSensor

    Basic int8 sensor.

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

    .. cpp:member:: OcaInt8 Reading

        This property has id ``5.1``.

        Int8 reading.

    .. cpp:function:: OcaStatus GetReading(OcaInt8 &Reading, OcaInt8 &minReading, OcaInt8 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt8 Reading: Output parameter.
        :param OcaInt8 minReading: Output parameter.
        :param OcaInt8 maxReading: Output parameter.

