.. _ocalibrary:

1.2.5  OcaLibrary
=================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaLibrary: OcaAgent

    A **library** is an agent that holds a collection of datasets. We
    refer to each dataset as a **Volume** . There are two kinds of
    volumes: **ParamSet** (parameter set). A ParamSet is a collection of
    operating parameter settings that can be applied to a block. Each
    ParamSet is associated with a specific block type, but not with a
    specific instance of that type. A ParamSet may be applied to any block
    instance of the associated type. A block's type is the object number
    of its factory or, for factory-defined blocks, a unique identifier set
    at time of manufacture. **Patch** . A Patch is a collection of
    ParamSet assignments. A ParamSet assigment is the description of a
    binding of a ParamSet to a block instance. To "apply" a Patch is to
    apply all of its assignments. To apply an assignment is to set all of
    its ParamSet's parameter values into its block. A given library
    instance can only hold one class of volume. A device that supports
    libraries can have any number of Patch and ParamSet libraries. If a
    device implements a Patch library, it must also implement at least one
    ParamSet library. However, the reverse is not true: a device may
    implement one or more ParamSet libraries without a Patch library.

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

    .. cpp:member:: OcaLibVolType VolumeType

        This property has id ``3.1``.

        Type of library volumes:

    .. cpp:member:: OcaLibAccess Access

        This property has id ``3.2``.

        Readonly, read-expand, or full.

    .. cpp:member:: OcaMap<OcaLibVolID, OcaLibVol> Volumes

        This property has id ``3.3``.

        Map of volumes held in the Library. Changed in version 2 because the
        definition of OcaLibVolMetaData, which is part of OcaLibVol, has
        changed, and because it is now a private property whose changes are
        signaled by the **OcaLibVolChanged** event.

    .. cpp:function:: OcaStatus AddVolume(OcaLibVol Volume, OcaLibVolID &ID)

        This method has id ``3.1``.

        Adds a volume to the library and returns its volume ID. The return
        value indicates whether the volume was successfully added. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part
        of OcaLibVol, has changed.

        :param OcaLibVol Volume: Input parameter.
        :param OcaLibVolID ID: Output parameter.

    .. cpp:function:: OcaStatus ReplaceVolume(OcaLibVolID ID, OcaLibVol Volume)

        This method has id ``3.2``.

        Replaces a volume in the library at the given volume ID. The return
        value indicates whether the volume was successfully replaced. Changed
        in version 2 because the definition of OcaLibVolMetaData, which is
        part of OcaLibVol, has changed.

        :param OcaLibVolID ID: Input parameter.
        :param OcaLibVol Volume: Input parameter.

    .. cpp:function:: OcaStatus DeleteVolume(OcaLibVolID ID)

        This method has id ``3.3``.

        Deletes a volume from the library. The return value indicates whether
        the group was successfully deleted.

        :param OcaLibVolID ID: Input parameter.

    .. cpp:function:: OcaStatus GetVolume(OcaLibVol &Volume)

        This method has id ``3.4``.

        Retrieves a library volume. The return value indicates whether the
        volume was successfully retrieved. Changed in version 2 because the
        definition of OcaLibVolMetaData, which is part of OcaLibVol, has
        changed.

        :param OcaLibVol Volume: Output parameter.

    .. cpp:function:: OcaStatus GetVolumeCount(OcaUint16 &Count)

        This method has id ``3.5``.

        Gets the count of volumes in this library. The return value indicates
        whether the count was successfully retrieved.

        :param OcaUint16 Count: Output parameter.

    .. cpp:function:: OcaStatus GetVolumes(OcaMap<OcaLibVolID, OcaLibVol> &Volumes)

        This method has id ``3.6``.

        Gets the list of volumes held in this library. The return value
        indicates whether the list was successfully retrieved. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part
        of OcaLibVol, has changed.

        :param OcaMap<OcaLibVolID, OcaLibVol> Volumes: Output parameter.

    .. cpp:function:: OcaStatus GetAccess(OcaLibAccess &Access)

        This method has id ``3.7``.

        Gets allowed access mode for this library. The return value indicates
        whether the property was successfully retrieved.

        :param OcaLibAccess Access: Output parameter.

    .. cpp:function:: OcaStatus SetAccess(OcaLibAccess Access)

        This method has id ``3.8``.

        Sets allowed access mode for this library. The return value indicates
        whether the property was successfully set. Not implemented for static,
        manufacturer-supplied libraries.

        :param OcaLibAccess Access: Input parameter.

