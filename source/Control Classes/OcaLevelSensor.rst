.. _ocalevelsensor:

1.1.2.2  OcaLevelSensor
=======================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaLevelSensor: OcaSensor

    Signal level sensor.

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

    .. cpp:member:: OcaDB Reading

        This property has id ``4.0``.

        dB reading.

    .. cpp:function:: OcaStatus GetReading(OcaDB &Reading, OcaDB &minReading, OcaDB &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaDB Reading: Output parameter.
        :param OcaDB minReading: Output parameter.
        :param OcaDB maxReading: Output parameter.

