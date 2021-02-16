.. _ocaimpedancesensor:

1.1.2.9  OcaImpedanceSensor
===========================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaImpedanceSensor: OcaSensor

    Basic impedance sensor. Value is complex (magnitude and phase).

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

    .. cpp:member:: OcaImpedance Reading

        This property has id ``4.1``.

        Impedance value (magnitude and phase).

    .. cpp:function:: OcaStatus GetReading(OcaImpedance &Reading, OcaImpedance &minReading, OcaImpedance &maxReading)

        This method has id ``4.1``.

        Gets the value and limits of the **Reading** property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaImpedance Reading: Output parameter.
        :param OcaImpedance minReading: Output parameter.
        :param OcaImpedance maxReading: Output parameter.

