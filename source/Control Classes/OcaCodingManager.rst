.. _ocacodingmanager:

1.3.12  OcaCodingManager
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaCodingManager <ocacodingmanager>`

.. cpp:class:: OcaCodingManager: OcaManager

    Optional manager that collects all media decoders/encoders (Codecs) which
    the device owns.

     - Must be instantiated in every device that implements more than one media
       encoding scheme and/or more than one media decoding scheme.

     - If instantiated, object number must be 12.



    **Properties**:


    .. _ocacodingmanager_availabledecodingschemes:

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableDecodingSchemes

        Map of names of media decoding schemes the device supports, indexed by
        scheme ID.

        This property has id ``3.2``.

    .. _ocacodingmanager_availableencodingschemes:

    .. cpp:member:: OcaMap<OcaMediaCodingSchemeID, OcaString> AvailableEncodingSchemes

        Map of names of media encoding schemes the device supports, indexed by
        scheme ID.

        This property has id ``3.1``.

    .. _ocacodingmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.12"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocacodingmanager_classversion:

    .. cpp:member:: static const OcaUint16 ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocacodingmanager_getavailableencodingschemes:

    .. cpp:function:: OcaStatus GetAvailableEncodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        Retrieves the map of available encoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        This method has id ``3.1``.

        - :cpp:expr:`Schemes`: Output parameter.


    .. _ocacodingmanager_getavailabledecodingschemes:

    .. cpp:function:: OcaStatus GetAvailableDecodingSchemes(OcaMap<OcaMediaCodingSchemeID, OcaString> &Schemes)

        Retrieves the map of available decoding schemes, indexed by scheme ID.
        Return value indicates success of the retrieval.

        This method has id ``3.2``.

        - :cpp:expr:`Schemes`: Output parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

