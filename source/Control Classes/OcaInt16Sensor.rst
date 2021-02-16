.. _ocaint16sensor:

1.1.2.1.3  OcaInt16Sensor
=========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaInt16Sensor: OcaBasicSensor

    Basic int16 sensor.

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

    .. cpp:member:: OcaInt16 Reading

        This property has id ``5.1``.

        Int16 reading.

    .. cpp:function:: OcaStatus GetReading(OcaInt16 &Reading, OcaInt16 &minReading, OcaInt16 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaInt16 Reading: Output parameter.
        :param OcaInt16 minReading: Output parameter.
        :param OcaInt16 maxReading: Output parameter.

