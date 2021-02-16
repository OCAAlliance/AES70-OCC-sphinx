.. _ocabasicsensor:

1.1.2.1  OcaBasicSensor
=======================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaBasicSensor: OcaSensor

    Abstract base class for weakly typed sensors.

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

