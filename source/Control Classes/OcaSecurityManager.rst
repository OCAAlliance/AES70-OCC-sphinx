.. _ocasecuritymanager:

1.3.2  OcaSecurityManager
=========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaSecurityManager <ocasecuritymanager>`

.. cpp:class:: OcaSecurityManager: OcaManager

    Manager that collects and controls security settings (including security
    keys).

     - Must be instantiated in every device that supports secure control and
       monitoring; otherwise, is optional.

     - May be instantiated at most once in any device.

     - If instantiated, object number must be 2.



    **Properties**:


    .. _ocasecuritymanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.2"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocasecuritymanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocasecuritymanager_securecontroldata:

    .. cpp:member:: OcaBoolean secureControlData

        Indicates whether the OCA control data in the system is secured.

        This property has id ``3.1``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocasecuritymanager_enablecontrolsecurity:

    .. cpp:function:: OcaStatus EnableControlSecurity()

        Enables security of control data (OCA messages). After calling this
        method all OCA messages are sent and received using a secure connection.
        The return value indicates whether the operation succeeded. If the
        operation fails security is not enabled.

        This method has id ``3.1``.

    .. _ocasecuritymanager_disablecontrolsecurity:

    .. cpp:function:: OcaStatus DisableControlSecurity()

        Disables security of control data (OCA messages). After calling this
        method all OCA messages can be sent and received both on insecure and
        secure connections. The return value indicates whether the operation
        succeeded. If the operation fails security is not disabled.

        This method has id ``3.2``.

    .. _ocasecuritymanager_changepresharedkey:

    .. cpp:function:: OcaStatus ChangePreSharedKey(OcaString identity, OcaBlob newKey)

        Changes the pre-shared key identified by the passed identity. Note that
        changing a PSK over the network will only work if the controller has a
        secure connection to the device and control security has been turned on.
        If this is not the case the method will return DeviceError.

        This method has id ``3.3``.

        - :cpp:expr:`identity`: Input parameter.


        - :cpp:expr:`newKey`: Input parameter.


    .. _ocasecuritymanager_addpresharedkey:

    .. cpp:function:: OcaStatus AddPreSharedKey(OcaString identity, OcaBlob key)

        Adds a pre-shared key (identified by the passed identity) to the device.
        By having multiple PSKs the device is able to participate in multiple
        secure systems. Note that adding a PSK over the network will only work
        if the controller has a secure connection to the device and control
        security has been turned on. If this is not the case the method will
        return DeviceError.

        This method has id ``3.4``.

        - :cpp:expr:`identity`: Input parameter.


        - :cpp:expr:`key`: Input parameter.


    .. _ocasecuritymanager_deletepresharedkey:

    .. cpp:function:: OcaStatus DeletePreSharedKey(OcaString identity)

        Deletes a pre-shared key (identified by the passed identity) on the
        device. After deleting the pre-shared key the device will no longer be
        able to participate in the secure system that uses the PSK. Note that
        deleting a PSK over the network will only work if the controller has a
        secure connection to the device and control security has been turned on.
        If this is not the case the method will return DeviceError.

        This method has id ``3.5``.

        - :cpp:expr:`identity`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::LockReadonly <ocaroot_lockreadonly>`

