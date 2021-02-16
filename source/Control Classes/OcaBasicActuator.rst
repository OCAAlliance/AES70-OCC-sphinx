.. _ocabasicactuator:

1.1.1.1  OcaBasicActuator
=========================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaBasicActuator: OcaActuator

    Abstract base class for weakly typed actuators.

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

