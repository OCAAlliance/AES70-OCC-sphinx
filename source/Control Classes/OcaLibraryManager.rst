.. _ocalibrarymanager:

1.3.8  OcaLibraryManager
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaLibraryManager <ocalibrarymanager>`

.. cpp:class:: OcaLibraryManager: OcaManager

    Optional manager for handling device presets -- Patch and ParamSet
    libraries.

     - May be instantiated once in any device.

     - If instantiated, object number must be 8.



    **Properties**:


    .. _ocalibrarymanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.8"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocalibrarymanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocalibrarymanager_libraries:

    .. cpp:member:: OcaList<OcaLibraryIdentifier> Libraries

        List of identifiers of all libraries in the device.

        This property has id ``3.1``.

    .. _ocalibrarymanager_currentpatch:

    .. cpp:member:: OcaLibVolIdentifier CurrentPatch

        Library volume identifier of the most-recently applied patch in this
        device. Changing the value of this property applies the patch
        represented by the new value.

        This property has id ``3.2``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocalibrarymanager_addlibrary:

    .. cpp:function:: OcaStatus AddLibrary(OcaLibVolType Type, OcaLibraryIdentifier &Identifier)

        Adds a library to the device. Return value indicates whether the library
        was successfully added.

        This method has id ``3.1``.

        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocalibrarymanager_deletelibrary:

    .. cpp:function:: OcaStatus DeleteLibrary(OcaONo ID)

        Deletes a library from the device.

        This method has id ``3.2``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocalibrarymanager_getlibrarycount:

    .. cpp:function:: OcaStatus GetLibraryCount(OcaLibVolType Type, OcaUint16 &Count)

        Returns the number of libraries of the given type that are instantiated
        in the device..

        This method has id ``3.3``.

        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`Count`: Output parameter.


    .. _ocalibrarymanager_getlibrarylist:

    .. cpp:function:: OcaStatus GetLibraryList(OcaLibVolType Type, OcaList<OcaLibraryIdentifier> &Libraries)

        Returns the list of object numbers of libraries of libraries of the
        given type that are instantiated in the device.

        This method has id ``3.4``.

        - :cpp:expr:`Type`: Input parameter.


        - :cpp:expr:`Libraries`: Output parameter.


    .. _ocalibrarymanager_getcurrentpatch:

    .. cpp:function:: OcaStatus GetCurrentPatch(OcaLibVolIdentifier &ID)

        Return the identifier of the most recently applied patch. The return
        value indicates whether the method succeeded.

        This method has id ``3.5``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocalibrarymanager_applypatch:

    .. cpp:function:: OcaStatus ApplyPatch(OcaLibVolIdentifier ID)

        Apply a patch to the device.

        This method has id ``3.6``.

        - :cpp:expr:`ID`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::LockReadonly <ocaroot_lockreadonly>`

