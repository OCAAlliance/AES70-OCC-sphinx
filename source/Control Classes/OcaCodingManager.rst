.. _ocacodingmanager:

1.3.12  OcaCodingManager
========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaCodingManager <ocacodingmanager>` 

.. cpp:class:: OcaCodingManager: OcaManager

    Optional manager that collects all media decoders/encoders (Codecs)
    which the device owns.
    
    - Must be instantiated in every device that implements more than one
    media encoding scheme and/or more than one media decoding scheme.
    
    
    - If instantiated, object number must be 12.
    

    **Properties**:

    .. _ocacodingmanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocacodingmanager_classversion:

    .. cpp:member:: OcaUint16 ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocacodingmanager_availableencodingschemes:

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableEncodingSchemes

        Map of names of media encoding schemes the device supports, indexed by
        scheme ID.

        This property has id ``3.1``.

    .. _ocacodingmanager_availabledecodingschemes:

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableDecodingSchemes

        Map of names of media decoding schemes the device supports, indexed by
        scheme ID.

        This property has id ``3.2``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocacodingmanager_getavailableencodingschemes:

    .. cpp:function:: OcaStatus GetAvailableEncodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        Retrieves the map of available encoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        This method has id ``3.1``.

        :param OcaMap<OcaMediaCodingSchemeID, OcaString> Schemes: Output parameter.

    .. _ocacodingmanager_getavailabledecodingschemes:

    .. cpp:function:: OcaStatus GetAvailableDecodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        Retrieves the map of available decoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        This method has id ``3.2``.

        :param OcaMap<OcaMediaCodingSchemeID, OcaString> Schemes: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
