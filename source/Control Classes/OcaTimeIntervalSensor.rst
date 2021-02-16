.. _ocatimeintervalsensor:

1.1.2.3  OcaTimeIntervalSensor
==============================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaTimeIntervalSensor: OcaSensor

    Time interval sensor.

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

    .. cpp:member:: OcaTimeInterval Reading

        This property has id ``4.1``.

        Time interval reading.

    .. cpp:function:: OcaStatus GetReading(OcaTimeInterval &Reading, OcaTimeInterval &minReading, OcaTimeInterval &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaTimeInterval Reading: Output parameter.
        :param OcaTimeInterval minReading: Output parameter.
        :param OcaTimeInterval maxReading: Output parameter.

