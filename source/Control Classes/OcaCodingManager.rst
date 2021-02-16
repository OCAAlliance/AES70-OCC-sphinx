.. _ocacodingmanager:

1.3.12  OcaCodingManager
========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaCodingManager: OcaManager

    Optional manager that collects all media decoders/encoders (Codecs)
    which the device owns.
    
    - Must be instantiated in every device that implements more than one
    media encoding scheme and/or more than one media decoding scheme.
    
    
    - If instantiated, object number must be 12.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaUint16 ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableEncodingSchemes

        This property has id ``3.1``.

        Map of names of media encoding schemes the device supports, indexed by
        scheme ID.

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableDecodingSchemes

        This property has id ``3.2``.

        Map of names of media decoding schemes the device supports, indexed by
        scheme ID.

    .. cpp:function:: OcaStatus GetAvailableEncodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        This method has id ``3.1``.

        Retrieves the map of available encoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        :param OcaMap<OcaMediaCodingSchemeID, OcaString> Schemes: Output parameter.

    .. cpp:function:: OcaStatus GetAvailableDecodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        This method has id ``3.2``.

        Retrieves the map of available decoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        :param OcaMap<OcaMediaCodingSchemeID, OcaString> Schemes: Output parameter.

