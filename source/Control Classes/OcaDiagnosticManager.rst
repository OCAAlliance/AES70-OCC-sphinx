.. _ocadiagnosticmanager:

1.3.13  OcaDiagnosticManager
============================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaDiagnosticManager: OcaManager

    Optional manager that provides application diagnostic aids. Unlike
    other manager classes, OcaDiagnosticManager may be subclassed to
    provide proprietary application diagnostic enhancements.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 13.
    

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

    .. cpp:function:: OcaStatus GetLockStatus(OcaONo ONo, OcaString &StatusDescription)

        This method has id ``3.1``.

        Retrieves a text description of the given object's lock status. Return
        value indicates success of the retrieval.

        :param OcaONo ONo: Input parameter.
        :param OcaString StatusDescription: Output parameter.

