.. _ocagainsensor:

1.1.2.10  OcaGainSensor
=======================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaGainSensor: OcaSensor

    Senses a gain value. Typically used to indicate instantaneous gain
    value of a dynamics element.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property. This is a new class in
        AES70-2018,

    .. cpp:member:: OcaDB Reading

        This property has id ``4.1``.

        Gain in dB

    .. cpp:function:: OcaStatus GetReading(OcaDB &Reading, OcaDB &minReading, OcaDB &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaDB Reading: Output parameter.
        :param OcaDB minReading: Output parameter.
        :param OcaDB maxReading: Output parameter.

