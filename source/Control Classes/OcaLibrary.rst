.. _ocalibrary:

1.2.5  OcaLibrary
=================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaLibrary <ocalibrary>`

.. cpp:class:: OcaLibrary: OcaAgent

    A **library** is an agent that holds a collection of datasets. We refer to
    each dataset as a **Volume**. There are two kinds of volumes: **ParamSet**
    (parameter set). A ParamSet is a collection of operating parameter settings
    that can be applied to a block. Each ParamSet is associated with a specific
    block type, but not with a specific instance of that type. A ParamSet may be
    applied to any block instance of the associated type. A block's type is the
    object number of its factory or, for factory-defined blocks, a unique
    identifier set at time of manufacture. **Patch**. A Patch is a collection of
    ParamSet assignments. A ParamSet assigment is the description of a binding
    of a ParamSet to a block instance. To "apply" a Patch is to apply all of its
    assignments. To apply an assignment is to set all of its ParamSet's
    parameter values into its block. A given library instance can only hold one
    class of volume. A device that supports libraries can have any number of
    Patch and ParamSet libraries. If a device implements a Patch library, it
    must also implement at least one ParamSet library. However, the reverse is
    not true: a device may implement one or more ParamSet libraries without a
    Patch library.

    **Properties**:


    .. _ocalibrary_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.5"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocalibrary_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

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

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocalibrary_addvolume:

    .. cpp:function:: OcaStatus AddVolume(OcaLibVol Volume, OcaLibVolID &ID)

        Adds a volume to the library and returns its volume ID. The return value
        indicates whether the volume was successfully added. Changed in version
        2 because the definition of OcaLibVolMetaData, which is part of
        OcaLibVol, has changed.

        This method has id ``3.1``.

        - :cpp:expr:`Volume`: Input parameter.


        - :cpp:expr:`ID`: Output parameter.


    .. _ocalibrary_replacevolume:

    .. cpp:function:: OcaStatus ReplaceVolume(OcaLibVolID ID, OcaLibVol Volume)

        Replaces a volume in the library at the given volume ID. The return
        value indicates whether the volume was successfully replaced. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part of
        OcaLibVol, has changed.

        This method has id ``3.2``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Volume`: Input parameter.


    .. _ocalibrary_deletevolume:

    .. cpp:function:: OcaStatus DeleteVolume(OcaLibVolID ID)

        Deletes a volume from the library. The return value indicates whether
        the group was successfully deleted.

        This method has id ``3.3``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocalibrary_getvolume:

    .. cpp:function:: OcaStatus GetVolume(OcaLibVolID ID, OcaLibVol &Volume)

        Retrieves a library volume. The return value indicates whether the
        volume was successfully retrieved. Changed in version 2 because the
        definition of OcaLibVolMetaData, which is part of OcaLibVol, has
        changed.

        This method has id ``3.4``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Volume`: Output parameter.


    .. _ocalibrary_getvolumecount:

    .. cpp:function:: OcaStatus GetVolumeCount(OcaUint16 &Count)

        Gets the count of volumes in this library. The return value indicates
        whether the count was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`Count`: Output parameter.


    .. _ocalibrary_getvolumes:

    .. cpp:function:: OcaStatus GetVolumes(OcaMap<OcaLibVolID, OcaLibVol> &Volumes)

        Gets the list of volumes held in this library. The return value
        indicates whether the list was successfully retrieved. Changed in
        version 2 because the definition of OcaLibVolMetaData, which is part of
        OcaLibVol, has changed.

        This method has id ``3.6``.

        - :cpp:expr:`Volumes`: Output parameter.


    .. _ocalibrary_getaccess:

    .. cpp:function:: OcaStatus GetAccess(OcaLibAccess &Access)

        Gets allowed access mode for this library. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.7``.

        - :cpp:expr:`Access`: Output parameter.


    .. _ocalibrary_setaccess:

    .. cpp:function:: OcaStatus SetAccess(OcaLibAccess Access)

        Sets allowed access mode for this library. The return value indicates
        whether the property was successfully set. Not implemented for static,
        manufacturer-supplied libraries.

        This method has id ``3.8``.

        - :cpp:expr:`Access`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`


    **Events**:


    .. _ocalibrary_ocalibvolchanged:

    .. cpp:function:: void OcaLibVolChanged(OcaLibVolChangedEventData eventData)

        Event that is raised whenever private property **Volumes** changes.
        Added in OcaLibrary Version 2.

        This event has id ``3.1``.
