.. _ocacurrentsensor:

1.1.2.8  OcaCurrentSensor
=========================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaCurrentSensor: OcaSensor

    Basic current sensor.

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

    .. cpp:member:: OcaCurrent Reading

        This property has id ``4.1``.

        Current value (amperes).

    .. cpp:function:: OcaStatus GetReading(OcaCurrent &Reading, OcaCurrent &minReading, OcaCurrent &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaCurrent Reading: Output parameter.
        :param OcaCurrent minReading: Output parameter.
        :param OcaCurrent maxReading: Output parameter.

