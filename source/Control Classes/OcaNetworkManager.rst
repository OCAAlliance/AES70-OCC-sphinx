.. _ocanetworkmanager:

1.3.6  OcaNetworkManager
========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaNetworkManager <ocanetworkmanager>` 

.. cpp:class:: OcaNetworkManager: OcaManager

    Optional manager that collects all media transport and control networks to which the device belongs.  
    
     - Must be instantiated once in every device that has more than one network object. In this context, "network object" shall mean an instance of  **OcaNetwork** ,  **OcaStreamNetwork** ,  **OcaApplicationNetwork** , or any subclass of these classes.
       
    
     - If instantiated, must have object number 6.
     

    **Properties**:

    .. _ocanetworkmanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocanetworkmanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property. Version 2 adds the control and media transport network properties and methods.

        This property has id ``3.2``.

    .. _ocanetworkmanager_networks:

    .. cpp:member:: OcaList<OcaONo> Networks

        Object numbers of  **OcaNetwork** objects, one for each network to which this device belongs.  **Deprecated as of OCA 1.2.** 

        This property has id ``3.1``.

    .. _ocanetworkmanager_streamnetworks:

    .. cpp:member:: OcaList<OcaONo> StreamNetworks

        Object numbers of  **OcaStreamNetwork** objects, one for each network to which this device belongs.  **Deprecated as of OCA 1.4.** 

        This property has id ``3.2``.

    .. _ocanetworkmanager_controlnetworks:

    .. cpp:member:: OcaList<OcaONo> ControlNetworks

        Object numbers of  **OcaControlNetwork** objects, one for each control network to which this device belongs. Added in version 2.

        This property has id ``3.3``.

    .. _ocanetworkmanager_mediatransportnetworks:

    .. cpp:member:: OcaList<OcaONo> MediaTransportNetworks

        Object numbers of  **OcaMediaTransportNetwork** objects, one for each media transport network to which this device belongs. Added in version 2.

        This property has id ``3.4``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocanetworkmanager_getnetworks:

    .. cpp:function:: OcaStatus GetNetworks(OcaList<OcaONo> &Networks)

        Gets the list of object numbers of  **OcaNetwork** instances in this device. Return value indicates whether the list was successfully retrieved.  **Deprecated as of OCA 1.2** 

        This method has id ``3.1``.

        :param OcaList<OcaONo> Networks: Output parameter.

    .. _ocanetworkmanager_getstreamnetworks:

    .. cpp:function:: OcaStatus GetStreamNetworks(OcaList<OcaONo> &StreamNetworks)

        Gets the list of object numbers of  **OcaStreamNetwork** instances in this device. Return value indicates whether list was successfully retrieved.  **Deprecated as of OCA 1.4.** 

        This method has id ``3.2``.

        :param OcaList<OcaONo> StreamNetworks: Output parameter.

    .. _ocanetworkmanager_getcontrolnetworks:

    .. cpp:function:: OcaStatus GetControlNetworks(OcaList<OcaONo> &ControlNetworks)

        Gets the list of object numbers of  **OcaControlNetwork** instances in this device. Return value indicates whether list was successfully retrieved. Introduced in version 1.4.

        This method has id ``3.3``.

        :param OcaList<OcaONo> ControlNetworks: Output parameter.

    .. _ocanetworkmanager_getmediatransportnetworks:

    .. cpp:function:: OcaStatus GetMediaTransportNetworks(OcaList<OcaONo> &MediaTransportNetworks)

        Gets the list of object numbers of  **OcaMediaTransportNetwork** instances in this device. Return value indicates whether list was successfully retrieved. Introduced in version 1.4.

        This method has id ``3.4``.

        :param OcaList<OcaONo> MediaTransportNetworks: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


