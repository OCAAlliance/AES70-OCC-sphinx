.. _ocaidentificationactuator:

1.1.1.21  OcaIdentificationActuator
===================================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaIdentificationActuator: OcaActuator

    Represents a function that turns on some kind of human-detectable
    indicator for purposes of device identification during network setup.
    Physical form of indicator is not defined by OCA, so it could be
    anything, e.g.
    
    - LED
    
    
    - Foghorn
    
    
    - Smoke emitter
    
    
    - Little waving robot hand wearing white glove
    
    
    - Jack-in-the-box popout
    
    
    - et cetera
    

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

    .. cpp:member:: OcaBoolean Active

        This property has id ``4.1``.

        True iff indicator is active.

    .. cpp:function:: OcaStatus GetActive(OcaBoolean &active)

        This method has id ``4.1``.

        Gets the current identification indicator activity state. The return
        value indicates whether the state was successfully retrieved.

        :param OcaBoolean active: Output parameter.

    .. cpp:function:: OcaStatus SetActive(OcaBoolean active)

        This method has id ``4.2``.

        Sets the Active state (i.e. value of the Active property). The return
        value indicates whether the state was successfully set.

        :param OcaBoolean active: Input parameter.

