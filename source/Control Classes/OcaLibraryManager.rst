.. _ocalibrarymanager:

1.3.8  OcaLibraryManager
========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaLibraryManager: OcaManager

    Optional manager for handling device presets -- Patch and ParamSet
    libraries.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 8.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaList<OcaLibraryIdentifier> Libraries

        This property has id ``3.0``.

        List of identifiers of all libraries in the device.

    .. cpp:member:: OcaLibVolIdentifier CurrentPatch

        This property has id ``3.0``.

        Library volume identifier of the most-recently applied patch in this
        device. Changing the value of this property applies the patch
        represented by the new value.

    .. cpp:function:: OcaStatus AddLibrary(OcaLibVolType Type, OcaLibraryIdentifier &Identifier)

        This method has id ``3.1``.

        Adds a library to the device. Return value indicates whether the
        library was successfully added.

        :param OcaLibVolType Type: Input parameter.
        :param OcaLibraryIdentifier Identifier: Output parameter.

    .. cpp:function:: OcaStatus DeleteLibrary(OcaONo ID)

        This method has id ``3.2``.

        Deletes a library from the device.

        :param OcaONo ID: Input parameter.

    .. cpp:function:: OcaStatus GetLibraryCount(OcaLibVolType Type, OcaUint16 &Count)

        This method has id ``3.3``.

        Returns the number of libraries of the given type that are
        instantiated in the device..

        :param OcaLibVolType Type: Input parameter.
        :param OcaUint16 Count: Output parameter.

    .. cpp:function:: OcaStatus GetLibraryList(OcaLibVolType Type, OcaList<OcaLibraryIdentifier> &Libraries)

        This method has id ``3.4``.

        Returns the list of object numbers of libraries of libraries of the
        given type that are instantiated in the device.

        :param OcaLibVolType Type: Input parameter.
        :param OcaList<OcaLibraryIdentifier> Libraries: Output parameter.

    .. cpp:function:: OcaStatus GetCurrentPatch(OcaLibVolIdentifier &ID)

        This method has id ``3.5``.

        Return the identifier of the most recently applied patch. The return
        value indicates whether the method succeeded.

        :param OcaLibVolIdentifier ID: Output parameter.

    .. cpp:function:: OcaStatus ApplyPatch(OcaLibVolIdentifier ID)

        This method has id ``3.6``.

        Apply a patch to the device.

        :param OcaLibVolIdentifier ID: Input parameter.

