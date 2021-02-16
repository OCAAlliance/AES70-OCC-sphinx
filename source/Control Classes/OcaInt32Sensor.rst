.. _ocaint32sensor:

1.1.2.1.4  OcaInt32Sensor
=========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaInt32Sensor: OcaBasicSensor

    Basic int32 sensor.

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

    .. cpp:member:: OcaInt32 Reading

        This property has id ``5.0``.

        Int32 reading.

    .. cpp:function:: OcaStatus GetReading(OcaInt32 &Reading, OcaInt32 &minReading, OcaInt32 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt32 Reading: Output parameter.
        :param OcaInt32 minReading: Output parameter.
        :param OcaInt32 maxReading: Output parameter.

