.. _ocabooleansensor:

1.1.2.1.1  OcaBooleanSensor
===========================

Extends :ref:`OcaBasicSensor <ocabasicsensor>`.

.. cpp:class:: OcaBooleanSensor: OcaBasicSensor

    Basic boolean sensor.

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

    .. cpp:member:: OcaBoolean Reading

        This property has id ``5.1``.

        Boolean reading.

    .. cpp:function:: OcaStatus GetReading(OcaBoolean &Reading)

        This method has id ``5.1``.

        Gets the **Reading** property. The return value indicates whether the
        data was successfully retrieved.

        :param OcaBoolean Reading: Output parameter.

