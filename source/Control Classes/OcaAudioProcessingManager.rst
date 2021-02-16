.. _ocaaudioprocessingmanager:

1.3.9  OcaAudioProcessingManager
================================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaAudioProcessingManager: OcaManager

    Placeholder for optional manager that in future versions of the
    standard will hold various global audio processing parameters.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 9.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

