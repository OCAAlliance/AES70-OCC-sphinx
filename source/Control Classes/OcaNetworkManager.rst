.. _ocanetworkmanager:

1.3.6  OcaNetworkManager
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaNetworkManager <ocanetworkmanager>`

.. cpp:class:: OcaNetworkManager: OcaManager

    Optional manager that collects all network interface and network application
    objects to which the device belongs.

     - Must be instantiated in every device that has more than one network
       object.

     - May be instantiated at most once in any device.

     - If instantiated, must have object number 6.



    **Properties**:


    .. _ocanetworkmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.6"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocanetworkmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocanetworkmanager_controlnetworks:

    .. cpp:member:: OcaList<OcaONo> ControlNetworks

        Object numbers of **OcaControlNetwork** objects, one for each control
        network to which this device belongs. Deprecated in version 3 of this
        class.

        This property has id ``3.3``.

    .. _ocanetworkmanager_mediatransportnetworks:

    .. cpp:member:: OcaList<OcaONo> MediaTransportNetworks

        Object numbers of **OcaMediaTransportNetwork** objects, one for each
        media transport network to which this device belongs. Deprecated in
        version 3 of this class.

        This property has id ``3.4``.

    .. _ocanetworkmanager_networkapplications:

    .. cpp:member:: OcaList<OcaONo> NetworkApplications

        Object numbers of all objects in this device that are instances of
        **OcaNetworkApplication** or a subclass of **OcaNetworkApplication**.
        Added in version 3 of this class.

        This property has id ``3.6``.

    .. _ocanetworkmanager_networkinterfaces:

    .. cpp:member:: OcaList<OcaONo> NetworkInterfaces

        Object numbers of all objects in this device that are instances of
        **OcaNetworkInterface** or a subclass of **OcaNetworkInterface**. Added
        in version 3 of this class.

        This property has id ``3.5``.

    .. _ocanetworkmanager_networks:

    .. cpp:member:: OcaList<OcaONo> Networks

        Object numbers of **OcaNetwork** objects, one for each network to which
        this device belongs. **Deprecated** in version 2 of this class.

        This property has id ``3.1``.

    .. _ocanetworkmanager_streamnetworks:

    .. cpp:member:: OcaList<OcaONo> StreamNetworks

        Object numbers of **OcaStreamNetwork** objects, one for each network to
        which this device belongs. **Deprecated** in version 3 of this class.

        This property has id ``3.2``.

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


    .. _ocanetworkmanager_getnetworks:

    .. cpp:function:: OcaStatus GetNetworks(OcaList<OcaONo> &Networks)

        Gets the list of object numbers of **OcaNetwork** instances in this
        device. **Deprecated** in version 2 of this class.

        This method has id ``3.1``.

        - :cpp:expr:`Networks`: Output parameter.


    .. _ocanetworkmanager_getstreamnetworks:

    .. cpp:function:: OcaStatus GetStreamNetworks(OcaList<OcaONo> &StreamNetworks)

        Gets the list of object numbers of **OcaStreamNetwork** objects in this
        device. **Deprecated** in version 2 of this class.

        This method has id ``3.2``.

        - :cpp:expr:`StreamNetworks`: Output parameter.


    .. _ocanetworkmanager_getcontrolnetworks:

    .. cpp:function:: OcaStatus GetControlNetworks(OcaList<OcaONo> &ControlNetworks)

        Gets the list of object numbers of **OcaControlNetwork** objects in this
        device. **Deprecated** in version 3 of this class.

        This method has id ``3.3``.

        - :cpp:expr:`ControlNetworks`: Output parameter.


    .. _ocanetworkmanager_getmediatransportnetworks:

    .. cpp:function:: OcaStatus GetMediaTransportNetworks(OcaList<OcaONo> &MediaTransportNetworks)

        Gets the list of object numbers of **OcaMediaTransportNetwork** objects
        in this device. **Deprecated** in version 3 of this class.

        This method has id ``3.4``.

        - :cpp:expr:`MediaTransportNetworks`: Output parameter.


    .. _ocanetworkmanager_getnetworkinterfaces:

    .. cpp:function:: OcaStatus GetNetworkInterfaces(OcaList<OcaONo> &ONos)

        Gets the list of object numbers of all objects that are instances of
        **OcaNetworkInterface** or a subclass of **OcaNetworkInterface.** Added
        in version 3 of this class.

        This method has id ``3.5``.

        - :cpp:expr:`ONos`: Output parameter.


    .. _ocanetworkmanager_getnetworkapplications:

    .. cpp:function:: OcaStatus GetNetworkApplications(OcaList<OcaONo> &ONos)

        Gets the list of object numbers of all objects that are instances of
        **OcaNetworkApplication** or a subclass of **OcaNetworkApplication.**
        Added in version 3 of this class.

        This method has id ``3.6``.

        - :cpp:expr:`ONos`: Output parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

