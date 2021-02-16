.. _ocasignalinput:

1.1.1.18  OcaSignalInput
========================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaSignalInput: OcaActuator

    A set of one or more non-network signal inputs. Number of channels is
    set at construction time. This class has no native properties or
    methods - they are all inherited from **OcaWorker** and above. It is
    defined as a separate class as an aid to enumeration and signal flow
    definition.

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

