.. _ocauint8sensor:

1.1.2.1.6  OcaUint8Sensor
=========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaUint8Sensor: OcaBasicSensor

    Basic uint8 sensor.

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

    .. cpp:member:: OcaUint8 Reading

        This property has id ``5.1``.

        Uint8 reading.

    .. cpp:function:: OcaStatus GetReading(OcaUint8 &Reading, OcaUint8 &minReading, OcaUint8 &maxReading)

        This method has id ``5.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaUint8 Reading: Output parameter.
        :param OcaUint8 minReading: Output parameter.
        :param OcaUint8 maxReading: Output parameter.

