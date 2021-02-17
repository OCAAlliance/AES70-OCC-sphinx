.. _ocalibrarymanager:

1.3.8  OcaLibraryManager
========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaLibraryManager <ocalibrarymanager>` 

.. cpp:class:: OcaLibraryManager: OcaManager

    Optional manager for handling device presets -- Patch and ParamSet
    libraries.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 8.
    

    **Properties**:

    .. _ocalibrarymanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocalibrarymanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

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

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocalibrarymanager_addlibrary:

    .. cpp:function:: OcaStatus AddLibrary(OcaLibVolType Type, OcaLibraryIdentifier &Identifier)

        Adds a library to the device. Return value indicates whether the
        library was successfully added.

        This method has id ``3.1``.

        :param OcaLibVolType Type: Input parameter.
        :param OcaLibraryIdentifier Identifier: Output parameter.

    .. _ocalibrarymanager_deletelibrary:

    .. cpp:function:: OcaStatus DeleteLibrary(OcaONo ID)

        Deletes a library from the device.

        This method has id ``3.2``.

        :param OcaONo ID: Input parameter.

    .. _ocalibrarymanager_getlibrarycount:

    .. cpp:function:: OcaStatus GetLibraryCount(OcaLibVolType Type, OcaUint16 &Count)

        Returns the number of libraries of the given type that are
        instantiated in the device..

        This method has id ``3.3``.

        :param OcaLibVolType Type: Input parameter.
        :param OcaUint16 Count: Output parameter.

    .. _ocalibrarymanager_getlibrarylist:

    .. cpp:function:: OcaStatus GetLibraryList(OcaLibVolType Type, OcaList<OcaLibraryIdentifier> &Libraries)

        Returns the list of object numbers of libraries of libraries of the
        given type that are instantiated in the device.

        This method has id ``3.4``.

        :param OcaLibVolType Type: Input parameter.
        :param OcaList<OcaLibraryIdentifier> Libraries: Output parameter.

    .. _ocalibrarymanager_getcurrentpatch:

    .. cpp:function:: OcaStatus GetCurrentPatch(OcaLibVolIdentifier &ID)

        Return the identifier of the most recently applied patch. The return
        value indicates whether the method succeeded.

        This method has id ``3.5``.

        :param OcaLibVolIdentifier ID: Output parameter.

    .. _ocalibrarymanager_applypatch:

    .. cpp:function:: OcaStatus ApplyPatch(OcaLibVolIdentifier ID)

        Apply a patch to the device.

        This method has id ``3.6``.

        :param OcaLibVolIdentifier ID: Input parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


