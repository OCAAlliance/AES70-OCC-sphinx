.. _ocadevicemanager:

1.3.1  OcaDeviceManager
=======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaDeviceManager <ocadevicemanager>`

.. cpp:class:: OcaDeviceManager: OcaManager

    Mandatory manager that contains information relevant to the whole device.

     - Must be instantiated once in every device.

     - Must have object number 1.



    **Properties**:


    .. _ocadevicemanager_busy:

    .. cpp:member:: OcaBoolean Busy

        True if and only if device is working on something and is not available
        for OCA command activity. Readonly. **Deprecated** in v3 of this class.

        This property has id ``3.10``.

    .. _ocadevicemanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadevicemanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocadevicemanager_controlenabled:

    .. cpp:member:: OcaBoolean ControlEnabled

        Indicates whether the device is enabled, i.e. whether it is responsive
        to OCA commands. Prior to v3 of this class, property name was
        **Enabled**.

        This property has id ``3.8``.

    .. _ocadevicemanager_devicename:

    .. cpp:member:: OcaString DeviceName

        User-specified name of this device in application context. Device
        instance name, not product name.

        This property has id ``3.4``.

    .. _ocadevicemanager_devicerevisionid:

    .. cpp:member:: const OcaString DeviceRevisionID

        Overall device revision identifier. Format of string is
        manufacturer-specific. Readonly. May be changed by proprietery functions
        of firmware upload processes. **Deprecated** in v3 of this class, moved
        into property **Product**.

        This property has id ``3.14``.

    .. _ocadevicemanager_devicerole:

    .. cpp:member:: OcaString DeviceRole

        Role of device in application (arbitrary). Named **Role** prior to v3 of
        this class.

        This property has id ``3.6``.

    .. _ocadevicemanager_loggingenabled:

    .. cpp:member:: OcaBoolean LoggingEnabled

        Global enable/disable switch for device logging. TRUE = logging enabled,
        FALSE = logging disabled. See class **OcaLog** for the rest of the
        logging mechanism.

        This property has id ``3.18``.

    .. _ocadevicemanager_managers:

    .. cpp:member:: OcaList<OcaManagerDescriptor> Managers

        List of all manager objects (including the Device Manager) instantiated
        in this device.

        This property has id ``3.13``.

    .. _ocadevicemanager_manufacturer:

    .. cpp:member:: const OcaManufacturer Manufacturer

        Descriptor of this product's manufacturer.

        This property has id ``3.15``.

    .. _ocadevicemanager_message:

    .. cpp:member:: OcaString Message

        Arbitrary text message provided by controller. Display and handling of
        the text is device-dependent and not defined by OCA.

        This property has id ``3.12``.

    .. _ocadevicemanager_modeldescription:

    .. cpp:member:: OcaModelDescription ModelDescription

        Read-only property that contains text names for this model, its
        manufacturer, and its version. **Deprecated** in v3 of this class, moved
        into property **Product**.

        This property has id ``3.3``.

    .. _ocadevicemanager_modelguid:

    .. cpp:member:: OcaModelGUID ModelGUID

        Read-only property that identifies the model of the device. Note this
        property is not equivalent to a MAC address, because (a) MAC addresses
        identify individual devices, not models, and (b) MAC addresses are
        Ethernet-specific, but an OCA device need not have an Ethernet port.
        **Deprecated** in v3 of this class, moved into property **Product** .

        This property has id ``3.1``.

    .. _ocadevicemanager_mostrecentpatchdatasetono:

    .. cpp:member:: OcaONo MostRecentPatchDatasetONo

        **ONo** of **OcaDataset** containing the most recently applied patch.
        Zero if no patch has been applied since last device reset.

        This property has id ``3.19``.

    .. _ocadevicemanager_ocaversion:

    .. cpp:member:: const OcaUint16 OcaVersion

        Read-only property that indicates the AES70 version number used by the
        device.

        This property has id ``3.5``.

    .. _ocadevicemanager_operationalstate:

    .. cpp:member:: OcaDeviceOperationalState OperationalState

        Operational state of device.

        This property has id ``3.17``.

    .. _ocadevicemanager_product:

    .. cpp:member:: const OcaProduct Product

        Descriptor of this product.

        This property has id ``3.16``.

    .. _ocadevicemanager_resetcause:

    .. cpp:member:: const OcaResetCause ResetCause

        Read-only property that indicates the cause of the last Device reset.

        This property has id ``3.11``.

    .. _ocadevicemanager_serialnumber:

    .. cpp:member:: const OcaString SerialNumber

        Read-only property that identifies the serial number of the Device.

        This property has id ``3.2``.

    .. _ocadevicemanager_state:

    .. cpp:member:: OcaDeviceState State

        Read-only property that indicates the current state of the device.
        Deprecated in v3 of this class, replaced by **.OperationalState** .

        This property has id ``3.9``.

    .. _ocadevicemanager_userinventorycode:

    .. cpp:member:: OcaString UserInventoryCode

        Code used for equipment tracking.

        This property has id ``3.7``.

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


    .. _ocadevicemanager_getocaversion:

    .. cpp:function:: OcaStatus GetOcaVersion(OcaUint16 &OcaVersion)

        Gets the value of the **OcaVersion** property.

        This method has id ``3.1``.

        - :cpp:expr:`OcaVersion`: Output parameter.


    .. _ocadevicemanager_getmodelguid:

    .. cpp:function:: OcaStatus GetModelGUID(OcaModelGUID &GUID)

        Gets the model GUID. **Deprecated** in v3 of this class, replaced by
        **GetProduct()** .

        This method has id ``3.2``.

        - :cpp:expr:`GUID`: Output parameter.


    .. _ocadevicemanager_getserialnumber:

    .. cpp:function:: OcaStatus GetSerialNumber(OcaString &serialNumber)

        Gets the value of the **SerialNumber** property.

        This method has id ``3.3``.

        - :cpp:expr:`serialNumber`: Output parameter.


    .. _ocadevicemanager_getdevicename:

    .. cpp:function:: OcaStatus GetDeviceName(OcaString &Name)

        Gets the device name.

        This method has id ``3.4``.

        - :cpp:expr:`Name`: Output parameter.


    .. _ocadevicemanager_setdevicename:

    .. cpp:function:: OcaStatus SetDeviceName(OcaString Name)

        Sets the device name.

        This method has id ``3.5``.

        - :cpp:expr:`Name`: Input parameter.


    .. _ocadevicemanager_getmodeldescription:

    .. cpp:function:: OcaStatus GetModelDescription(OcaModelDescription &Description)

        Gets the model description. **Deprecated** in v3 of this class, replaced
        by** GetProduct()** .

        This method has id ``3.6``.

        - :cpp:expr:`Description`: Output parameter.


    .. _ocadevicemanager_getdevicerole:

    .. cpp:function:: OcaStatus GetDeviceRole(OcaString &role)

        Gets the value of the **DeviceRole** property.

        This method has id ``3.7``.

        - :cpp:expr:`role`: Output parameter.


    .. _ocadevicemanager_setdevicerole:

    .. cpp:function:: OcaStatus SetDeviceRole(OcaString role)

        Sets the value of the **DeviceRole** property.

        This method has id ``3.8``.

        - :cpp:expr:`role`: Input parameter.


    .. _ocadevicemanager_getuserinventorycode:

    .. cpp:function:: OcaStatus GetUserInventoryCode(OcaString &Code)

        Gets the value of the **UserInventoryCode** property.

        This method has id ``3.9``.

        - :cpp:expr:`Code`: Output parameter.


    .. _ocadevicemanager_setuserinventorycode:

    .. cpp:function:: OcaStatus SetUserInventoryCode(OcaString Code)

        Sets the value of the **UserInventoryCode** property.

        This method has id ``3.10``.

        - :cpp:expr:`Code`: Input parameter.


    .. _ocadevicemanager_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        Gets the value of the **Enabled** property. Deprecated in v3 of this
        class.

        This method has id ``3.11``.

        - :cpp:expr:`enabled`: Output parameter.


    .. _ocadevicemanager_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        Sets the value of the **Enabled** property. Deprecated in v3 of this
        class.

        This method has id ``3.12``.

        - :cpp:expr:`enabled`: Input parameter.


    .. _ocadevicemanager_getstate:

    .. cpp:function:: OcaStatus GetState(OcaDeviceState &state)

        Gets the value of the State property. **Deprecated** in v3 of this
        class, replaced by **.GetOperationalState() .**

        This method has id ``3.13``.

        - :cpp:expr:`state`: Output parameter.


    .. _ocadevicemanager_setresetkey:

    .. cpp:function:: OcaStatus SetResetKey(OcaBlobFixedLen<16> Key, OcaNetworkAddress Address)

        Sets the value of the reset key and the required source address for the
        reset command. If given address is null, all source addresses will be
        accepted.

        This method has id ``3.14``.

        - :cpp:expr:`Key`: Input parameter.


        - :cpp:expr:`Address`: Input parameter.


    .. _ocadevicemanager_getresetcause:

    .. cpp:function:: OcaStatus GetResetCause(OcaResetCause &resetCause)

        Gets the value of the **ResetCause** property.

        This method has id ``3.15``.

        - :cpp:expr:`resetCause`: Output parameter.


    .. _ocadevicemanager_clearresetcause:

    .. cpp:function:: OcaStatus ClearResetCause()

        Clears the **ResetCause** property, i.e. resets it to the default value
        'PowerOn'. Must be used after the reset cause has been read out to
        ensure differentiation between reconnects due to network loss and
        reconnects due to external or internal reset. Offered as a separate
        method (instead of implicitly clearing the cause after it has been read
        out) to accommodate systems that have multiple controllers.

        This method has id ``3.16``.

    .. _ocadevicemanager_getmessage:

    .. cpp:function:: OcaStatus GetMessage(OcaString &Message)

        Gets the value of property **Message**.

        This method has id ``3.17``.

        - :cpp:expr:`Message`: Output parameter.


    .. _ocadevicemanager_setmessage:

    .. cpp:function:: OcaStatus SetMessage(OcaString Text)

        Set arbitrary text message into **Message** property.

        This method has id ``3.18``.

        - :cpp:expr:`Text`: Input parameter.


    .. _ocadevicemanager_getmanagers:

    .. cpp:function:: OcaStatus GetManagers(OcaList<OcaManagerDescriptor> &Managers)

        Retrive the list of descriptors of managers instantiated in this device.

        This method has id ``3.19``.

        - :cpp:expr:`Managers`: Output parameter.


    .. _ocadevicemanager_getdevicerevisionid:

    .. cpp:function:: OcaStatus GetDeviceRevisionID(OcaString &ID)

        Gets the value of deprecated property **DeviceRevisionID**.
        **Deprecated** in v3 of this class, replaced by **.GetProduct()** .

        This method has id ``3.20``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocadevicemanager_getmanufacturer:

    .. cpp:function:: OcaStatus GetManufacturer(OcaManufacturer &Manufacturer)

        Gets the device's manufacturer descriptor.

        This method has id ``3.21``.

        - :cpp:expr:`Manufacturer`: Output parameter.


    .. _ocadevicemanager_getproduct:

    .. cpp:function:: OcaStatus GetProduct(OcaProduct &Product)

        Gets the device's product descriptor.

        This method has id ``3.22``.

        - :cpp:expr:`Product`: Output parameter.


    .. _ocadevicemanager_getoperationalstate:

    .. cpp:function:: OcaStatus GetOperationalState(OcaDeviceOperationalState &State)

        Gets the device's operational state.

        This method has id ``3.23``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocadevicemanager_getloggingenabled:

    .. cpp:function:: OcaStatus GetLoggingEnabled(OcaBoolean &Enabled)

        Gets the value of property **LoggingEnabled**.

        This method has id ``3.24``.

        - :cpp:expr:`Enabled`: Output parameter.


    .. _ocadevicemanager_setloggingenabled:

    .. cpp:function:: OcaStatus SetLoggingEnabled(OcaBoolean Enabled)

        Sets the value of property **LoggingEnabled**.

        This method has id ``3.25``.

        - :cpp:expr:`Enabled`: Input parameter.


    .. _ocadevicemanager_getmostrecentpatchdatasetono:

    .. cpp:function:: OcaStatus GetMostRecentPatchDatasetONo(OcaONo &ONo)

        Gets the value of property **MostRecentPatchDatasetONo**.

        This method has id ``3.26``.

        - :cpp:expr:`ONo`: Output parameter.


    .. _ocadevicemanager_applypatch:

    .. cpp:function:: OcaStatus ApplyPatch(OcaONo ONo)

        Applies the patch in the **OcaDataset** identified by the given **ONo**,
        and sets the value of property MostRecentPatchDatasetONo.

        This method has id ``3.27``.

        - :cpp:expr:`ONo`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

