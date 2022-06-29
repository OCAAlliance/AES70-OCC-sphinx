.. _ocasecuritymanager:

1.3.2  OcaSecurityManager
=========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaSecurityManager <ocasecuritymanager>` 

.. cpp:class:: OcaSecurityManager: OcaManager

    Manager that collects and controls security settings (including security keys).  
    
     - Must be instantiated in every device that supports secure control and monitoring; otherwise, is optional.
     
    
     - May be instantiated at most once in any device.
     
    
     - If instantiated, object number must be 2.
     

    **Properties**:

    .. _ocasecuritymanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.2"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocasecuritymanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocasecuritymanager_securecontroldata:

    .. cpp:member:: OcaBoolean secureControlData

        Indicates whether the OCA control data in the system is secured.

        This property has id ``3.1``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocasecuritymanager_addpresharedkey:

    .. cpp:function:: OcaStatus AddPreSharedKey(OcaString identity, OcaBlob key)

        Adds a pre-shared key (identified by the passed identity) to the device. By having multiple PSKs the device is able to participate in multiple secure systems. Note that adding a PSK over the network will only work if the controller has a secure connection to the device and control security has been turned on. If this is not the case the method will return DeviceError.

        This method has id ``3.4``.

        :param OcaString identity: Input parameter.
        :param OcaBlob key: Input parameter.

    .. _ocasecuritymanager_changepresharedkey:

    .. cpp:function:: OcaStatus ChangePreSharedKey(OcaString identity, OcaBlob newKey)

        Changes the pre-shared key identified by the passed identity. Note that changing a PSK over the network will only work if the controller has a secure connection to the device and control security has been turned on. If this is not the case the method will return DeviceError.

        This method has id ``3.3``.

        :param OcaString identity: Input parameter.
        :param OcaBlob newKey: Input parameter.

    .. _ocasecuritymanager_deletepresharedkey:

    .. cpp:function:: OcaStatus DeletePreSharedKey(OcaString identity)

        Deletes a pre-shared key (identified by the passed identity) on the device. After deleting the pre-shared key the device will no longer be able to participate in the secure system that uses the PSK. Note that deleting a PSK over the network will only work if the controller has a secure connection to the device and control security has been turned on. If this is not the case the method will return DeviceError.

        This method has id ``3.5``.

        :param OcaString identity: Input parameter.

    .. _ocasecuritymanager_disablecontrolsecurity:

    .. cpp:function:: OcaStatus DisableControlSecurity()

        Disables security of control data (OCA messages). After calling this method all OCA messages can be sent and received both on insecure and secure connections. The return value indicates whether the operation succeeded. If the operation fails security is not disabled.

        This method has id ``3.2``.


    .. _ocasecuritymanager_enablecontrolsecurity:

    .. cpp:function:: OcaStatus EnableControlSecurity()

        Enables security of control data (OCA messages). After calling this method all OCA messages are sent and received using a secure connection. The return value indicates whether the operation succeeded. If the operation fails security is not enabled.

        This method has id ``3.1``.



    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


