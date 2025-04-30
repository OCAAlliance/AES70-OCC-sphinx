.. _ocanetworkmanager:

1.3.6  OcaNetworkManager
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaNetworkManager <ocanetworkmanager>`

.. cpp:class:: OcaNetworkManager: OcaManager

    Optional manager that collects all media transport and control networks to
    which the device belongs.

     - Must be instantiated once in every device that has more than one network
       object. In this context, "network object" shall mean an instance of
       **OcaNetwork**, **OcaStreamNetwork**, **OcaApplicationNetwork**, or any
       subclass of these classes.

     - If instantiated, must have object number 6.



    **Properties**:


    .. _ocanetworkmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.6"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocanetworkmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property. Version 2 adds the control and media
        transport network properties and methods.

        This property has id ``1.2``.

    .. _ocanetworkmanager_networks:

    .. cpp:member:: OcaList<OcaONo> Networks

        Object numbers of **OcaNetwork** objects, one for each network to which
        this device belongs. **Deprecated as of OCA 1.2.**

        This property has id ``3.1``.

    .. _ocanetworkmanager_streamnetworks:

    .. cpp:member:: OcaList<OcaONo> StreamNetworks

        Object numbers of **OcaStreamNetwork** objects, one for each network to
        which this device belongs. **Deprecated as of OCA 1.4.**

        This property has id ``3.2``.

    .. _ocanetworkmanager_controlnetworks:

    .. cpp:member:: OcaList<OcaONo> ControlNetworks

        Object numbers of **OcaControlNetwork** objects, one for each control
        network to which this device belongs. Added in version 2.

        This property has id ``3.3``.

    .. _ocanetworkmanager_mediatransportnetworks:

    .. cpp:member:: OcaList<OcaONo> MediaTransportNetworks

        Object numbers of **OcaMediaTransportNetwork** objects, one for each
        media transport network to which this device belongs. Added in version
        2.

        This property has id ``3.4``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocanetworkmanager_getnetworks:

    .. cpp:function:: OcaStatus GetNetworks(OcaList<OcaONo> &Networks)

        Gets the list of object numbers of **OcaNetwork** instances in this
        device. Return value indicates whether the list was successfully
        retrieved. **Deprecated as of OCA 1.2**

        This method has id ``3.1``.

        - :cpp:expr:`Networks`: Output parameter.


    .. _ocanetworkmanager_getstreamnetworks:

    .. cpp:function:: OcaStatus GetStreamNetworks(OcaList<OcaONo> &StreamNetworks)

        Gets the list of object numbers of **OcaStreamNetwork** instances in
        this device. Return value indicates whether list was successfully
        retrieved. **Deprecated as of OCA 1.4.**

        This method has id ``3.2``.

        - :cpp:expr:`StreamNetworks`: Output parameter.


    .. _ocanetworkmanager_getcontrolnetworks:

    .. cpp:function:: OcaStatus GetControlNetworks(OcaList<OcaONo> &ControlNetworks)

        Gets the list of object numbers of **OcaControlNetwork** instances in
        this device. Return value indicates whether list was successfully
        retrieved. Introduced in version 1.4.

        This method has id ``3.3``.

        - :cpp:expr:`ControlNetworks`: Output parameter.


    .. _ocanetworkmanager_getmediatransportnetworks:

    .. cpp:function:: OcaStatus GetMediaTransportNetworks(OcaList<OcaONo> &MediaTransportNetworks)

        Gets the list of object numbers of **OcaMediaTransportNetwork**
        instances in this device. Return value indicates whether list was
        successfully retrieved. Introduced in version 1.4.

        This method has id ``3.4``.

        - :cpp:expr:`MediaTransportNetworks`: Output parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::LockReadonly <ocaroot_lockreadonly>`

