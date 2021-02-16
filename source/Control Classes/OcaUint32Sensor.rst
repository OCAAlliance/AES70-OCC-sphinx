.. _ocauint32sensor:

1.1.2.1.8  OcaUint32Sensor
==========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaUint32Sensor: OcaBasicSensor

    Basic uint32 sensor.

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

    .. cpp:member:: OcaUint32 Reading

        This property has id ``5.0``.

        Uint32 reading.

    .. cpp:function:: OcaStatus GetReading(OcaUint32 &Reading, OcaUint32 &minReading, OcaUint32 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaUint32 Reading: Output parameter.
        :param OcaUint32 minReading: Output parameter.
        :param OcaUint32 maxReading: Output parameter.

