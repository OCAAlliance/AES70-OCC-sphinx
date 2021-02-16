.. _ocanetworkmanager:

1.3.6  OcaNetworkManager
========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaNetworkManager: OcaManager

    Optional manager that collects all media transport and control
    networks to which the device belongs.
    
    - Must be instantiated once in every device that has more than one
    network object. In this context, "network object" shall mean an
    instance of **OcaNetwork** , **OcaStreamNetwork** ,
    **OcaApplicationNetwork** , or any subclass of these classes.
    
    
    - If instantiated, must have object number 6.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property. Version 2 adds the control and
        media transport network properties and methods.

    .. cpp:member:: OcaList<OcaONo> Networks

        This property has id ``3.1``.

        Object numbers of **OcaNetwork** objects, one for each network to
        which this device belongs. **Deprecated as of OCA 1.2.**

    .. cpp:member:: OcaList<OcaONo> StreamNetworks

        This property has id ``3.2``.

        Object numbers of **OcaStreamNetwork** objects, one for each network
        to which this device belongs. **Deprecated as of OCA 1.4.**

    .. cpp:member:: OcaList<OcaONo> ControlNetworks

        This property has id ``3.3``.

        Object numbers of **OcaControlNetwork** objects, one for each control
        network to which this device belongs. Added in version 2.

    .. cpp:member:: OcaList<OcaONo> MediaTransportNetworks

        This property has id ``3.4``.

        Object numbers of **OcaMediaTransportNetwork** objects, one for each
        media transport network to which this device belongs. Added in version
        2.

    .. cpp:function:: OcaStatus GetNetworks(OcaList<OcaONo> &Networks)

        This method has id ``3.1``.

        Gets the list of object numbers of **OcaNetwork** instances in this
        device. Return value indicates whether the list was successfully
        retrieved. **Deprecated as of OCA 1.2**

        :param OcaList<OcaONo> Networks: Output parameter.

    .. cpp:function:: OcaStatus GetStreamNetworks(OcaList<OcaONo> &StreamNetworks)

        This method has id ``3.2``.

        Gets the list of object numbers of **OcaStreamNetwork** instances in
        this device. Return value indicates whether list was successfully
        retrieved. **Deprecated as of OCA 1.4.**

        :param OcaList<OcaONo> StreamNetworks: Output parameter.

    .. cpp:function:: OcaStatus GetControlNetworks(OcaList<OcaONo> &ControlNetworks)

        This method has id ``3.3``.

        Gets the list of object numbers of **OcaControlNetwork** instances in
        this device. Return value indicates whether list was successfully
        retrieved. Introduced in version 1.4.

        :param OcaList<OcaONo> ControlNetworks: Output parameter.

    .. cpp:function:: OcaStatus GetMediaTransportNetworks(OcaList<OcaONo> &MediaTransportNetworks)

        This method has id ``3.4``.

        Gets the list of object numbers of **OcaMediaTransportNetwork**
        instances in this device. Return value indicates whether list was
        successfully retrieved. Introduced in version 1.4.

        :param OcaList<OcaONo> MediaTransportNetworks: Output parameter.

