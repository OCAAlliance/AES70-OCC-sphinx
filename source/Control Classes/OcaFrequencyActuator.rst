.. _ocafrequencyactuator:

1.1.1.8  OcaFrequencyActuator
=============================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFrequencyActuator: OcaActuator

    Simple frequency actuator.

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

    .. cpp:member:: OcaFrequency Frequency

        This property has id ``4.0``.

        Frequency in Hertz.

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        This method has id ``4.1``.

        Gets the value of the Frequency property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaFrequency Frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency Frequency)

        This method has id ``4.2``.

        Sets the value of the Frequency property. The return value indicates
        whether the property was successfully set.

        :param OcaFrequency Frequency: Input parameter.

