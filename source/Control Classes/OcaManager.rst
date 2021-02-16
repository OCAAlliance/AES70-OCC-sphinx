.. _ocamanager:

1.3  OcaManager
===============

Extends :ref:`OcaRoot <ocaroot>`.

.. cpp:class:: OcaManager: OcaRoot

    Abstract base class for classes that represent non-audio (i.e. control
    and monitoring) functions. All concrete manager objects are lockable
    (the constructor of this class initializes the Root object with
    property Lockable true).

    .. cpp:member:: OcaClassID ClassID

        This property has id ``2.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``2.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

