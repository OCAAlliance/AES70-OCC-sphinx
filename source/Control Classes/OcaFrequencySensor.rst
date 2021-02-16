.. _ocafrequencysensor:

1.1.2.4  OcaFrequencySensor
===========================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaFrequencySensor: OcaSensor

    Frequency sensor.

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

    .. cpp:member:: OcaFrequency Reading

        This property has id ``4.0``.

        Frequency value.

    .. cpp:function:: OcaStatus GetReading(OcaFrequency &Reading, OcaFrequency &minReading, OcaFrequency &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaFrequency Reading: Output parameter.
        :param OcaFrequency minReading: Output parameter.
        :param OcaFrequency maxReading: Output parameter.

