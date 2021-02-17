.. _ocalibrary:

1.2.5  OcaLibrary
=================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaLibrary <ocalibrary>` 

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

    **Properties**:

    .. _ocalibrary_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocalibrary_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocalibrary_volumetype:

    .. cpp:member:: OcaLibVolType VolumeType

        Type of library volumes:

        This property has id ``3.1``.

    .. _ocalibrary_access:

    .. cpp:member:: OcaLibAccess Access

        Readonly, read-expand, or full.

        This property has id ``3.2``.

    .. _ocalibrary_volumes:

    .. cpp:member:: OcaMap<OcaLibVolID, OcaLibVol> Volumes

        Map of volumes held in the Library. Changed in version 2 because the
        definition of OcaLibVolMetaData, which is part of OcaLibVol, has
        changed, and because it is now a private property whose changes are
        signaled by the **OcaLibVolChanged** event.

        This property has id ``3.3``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocalibrary_addvolume:

    .. cpp:function:: OcaStatus AddVolume(OcaLibVol Volume, OcaLibVolID &ID)

        Adds a volume to the library and returns its volume ID. The return
        value indicates whether the volume was successfully added. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part
        of OcaLibVol, has changed.

        This method has id ``3.1``.

        :param OcaLibVol Volume: Input parameter.
        :param OcaLibVolID ID: Output parameter.

    .. _ocalibrary_replacevolume:

    .. cpp:function:: OcaStatus ReplaceVolume(OcaLibVolID ID, OcaLibVol Volume)

        Replaces a volume in the library at the given volume ID. The return
        value indicates whether the volume was successfully replaced. Changed
        in version 2 because the definition of OcaLibVolMetaData, which is
        part of OcaLibVol, has changed.

        This method has id ``3.2``.

        :param OcaLibVolID ID: Input parameter.
        :param OcaLibVol Volume: Input parameter.

    .. _ocalibrary_deletevolume:

    .. cpp:function:: OcaStatus DeleteVolume(OcaLibVolID ID)

        Deletes a volume from the library. The return value indicates whether
        the group was successfully deleted.

        This method has id ``3.3``.

        :param OcaLibVolID ID: Input parameter.

    .. _ocalibrary_getvolume:

    .. cpp:function:: OcaStatus GetVolume(OcaLibVol &Volume)

        Retrieves a library volume. The return value indicates whether the
        volume was successfully retrieved. Changed in version 2 because the
        definition of OcaLibVolMetaData, which is part of OcaLibVol, has
        changed.

        This method has id ``3.4``.

        :param OcaLibVol Volume: Output parameter.

    .. _ocalibrary_getvolumecount:

    .. cpp:function:: OcaStatus GetVolumeCount(OcaUint16 &Count)

        Gets the count of volumes in this library. The return value indicates
        whether the count was successfully retrieved.

        This method has id ``3.5``.

        :param OcaUint16 Count: Output parameter.

    .. _ocalibrary_getvolumes:

    .. cpp:function:: OcaStatus GetVolumes(OcaMap<OcaLibVolID, OcaLibVol> &Volumes)

        Gets the list of volumes held in this library. The return value
        indicates whether the list was successfully retrieved. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part
        of OcaLibVol, has changed.

        This method has id ``3.6``.

        :param OcaMap<OcaLibVolID, OcaLibVol> Volumes: Output parameter.

    .. _ocalibrary_getaccess:

    .. cpp:function:: OcaStatus GetAccess(OcaLibAccess &Access)

        Gets allowed access mode for this library. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.7``.

        :param OcaLibAccess Access: Output parameter.

    .. _ocalibrary_setaccess:

    .. cpp:function:: OcaStatus SetAccess(OcaLibAccess Access)

        Sets allowed access mode for this library. The return value indicates
        whether the property was successfully set. Not implemented for static,
        manufacturer-supplied libraries.

        This method has id ``3.8``.

        :param OcaLibAccess Access: Input parameter.


    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
