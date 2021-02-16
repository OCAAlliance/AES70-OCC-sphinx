.. _ocasecuritymanager:

1.3.2  OcaSecurityManager
=========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaSecurityManager: OcaManager

    Manager that collects and controls security settings (including
    security keys).
    
    - Must be instantiated in every device that supports secure control
    and monitoring; otherwise, is optional.
    
    
    - May be instantiated at most once in any device.
    
    
    - If instantiated, object number must be 2.
    

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

    .. cpp:member:: OcaBoolean secureControlData

        This property has id ``3.0``.

        Indicates whether the OCA control data in the system is secured.

    .. cpp:function:: OcaStatus AddPreSharedKey(OcaString identity, OcaBlob key)

        This method has id ``3.4``.

        Adds a pre-shared key (identified by the passed identity) to the
        device. By having multiple PSKs the device is able to participate in
        multiple secure systems. Note that adding a PSK over the network will
        only work if the controller has a secure connection to the device and
        control security has been turned on. If this is not the case the
        method will return DeviceError.

        :param OcaString identity: Input parameter.
        :param OcaBlob key: Input parameter.

    .. cpp:function:: OcaStatus ChangePreSharedKey(OcaString identity, OcaBlob newKey)

        This method has id ``3.3``.

        Changes the pre-shared key identified by the passed identity. Note
        that changing a PSK over the network will only work if the controller
        has a secure connection to the device and control security has been
        turned on. If this is not the case the method will return DeviceError.

        :param OcaString identity: Input parameter.
        :param OcaBlob newKey: Input parameter.

    .. cpp:function:: OcaStatus DeletePreSharedKey(OcaString identity)

        This method has id ``3.5``.

        Deletes a pre-shared key (identified by the passed identity) on the
        device. After deleting the pre-shared key the device will no longer be
        able to participate in the secure system that uses the PSK. Note that
        deleting a PSK over the network will only work if the controller has a
        secure connection to the device and control security has been turned
        on. If this is not the case the method will return DeviceError.

        :param OcaString identity: Input parameter.

    .. cpp:function:: OcaStatus DisableControlSecurity()

        This method has id ``3.2``.

        Disables security of control data (OCA messages). After calling this
        method all OCA messages can be sent and received both on insecure and
        secure connections. The return value indicates whether the operation
        succeeded. If the operation fails security is not disabled.


    .. cpp:function:: OcaStatus EnableControlSecurity()

        This method has id ``3.1``.

        Enables security of control data (OCA messages). After calling this
        method all OCA messages are sent and received using a secure
        connection. The return value indicates whether the operation
        succeeded. If the operation fails security is not enabled.


