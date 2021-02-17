.. _ocadevicemanager:

1.3.1  OcaDeviceManager
=======================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaDeviceManager <ocadevicemanager>` 

.. cpp:class:: OcaDeviceManager: OcaManager

    Mandatory manager that contains information relevant to the whole
    device.
    
    - Must be instantiated once in every device.
    
    
    - Must have object number 1.
    

    **Properties**:

    .. _ocadevicemanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocadevicemanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocadevicemanager_modelguid:

    .. cpp:member:: OcaModelGUID ModelGUID

        Read-only property that identifies the model of the device. Note this
        property is not equivalent to a MAC address, because (a) MAC addresses
        identify individual devices, not models, and (b) MAC addresses are
        Ethernet-specific, but an OCA device need not have an Ethernet port.

        This property has id ``3.1``.

    .. _ocadevicemanager_serialnumber:

    .. cpp:member:: OcaString SerialNumber

        Read-only property that identifies the serial number of the CAP
        device.

        This property has id ``3.2``.

    .. _ocadevicemanager_modeldescription:

    .. cpp:member:: OcaModelDescription ModelDescription

        Read-only property that contains text names for this model, its
        manufacturer, and its version.

        This property has id ``3.3``.

    .. _ocadevicemanager_devicename:

    .. cpp:member:: OcaString DeviceName

        Name of the device. Should be unique manufacturer-qualified
        identifier.

        This property has id ``3.4``.

    .. _ocadevicemanager_ocaversion:

    .. cpp:member:: OcaUint16 OcaVersion

        Read-only property that indicates the AES70 version number used by the
        device.

        This property has id ``3.5``.

    .. _ocadevicemanager_devicerole:

    .. cpp:member:: OcaString DeviceRole

        Role of device in application (arbitrary).

        This property has id ``3.6``.

    .. _ocadevicemanager_userinventorycode:

    .. cpp:member:: OcaString UserInventoryCode

        Code used for equipment tracking.

        This property has id ``3.7``.

    .. _ocadevicemanager_enabled:

    .. cpp:member:: OcaBoolean Enabled

        Indicates whether the device is enabled (and therefore operational).

        This property has id ``3.8``.

    .. _ocadevicemanager_state:

    .. cpp:member:: OcaDeviceState State

        Read-only property that indicates the current state of the device.

        This property has id ``3.9``.

    .. _ocadevicemanager_busy:

    .. cpp:member:: OcaBoolean Busy

        True iff device is working on something and is not available for OCA
        command activity. Readonly.

        This property has id ``3.10``.

    .. _ocadevicemanager_resetcause:

    .. cpp:member:: OcaResetCause ResetCause

        Read-only attribute that indicates the reset cause of the last reset.

        This property has id ``3.11``.

    .. _ocadevicemanager_message:

    .. cpp:member:: OcaString Message

        Arbitrary text message provided by controller. Display and handling of
        the text is device-dependent and not defined by OCA.

        This property has id ``3.12``.

    .. _ocadevicemanager_managers:

    .. cpp:member:: OcaList<OcaManagerDescriptor> Managers

        List of all manager objects instantiated in this device.

        This property has id ``3.13``.

    .. _ocadevicemanager_devicerevisionid:

    .. cpp:member:: OcaString DeviceRevisionID

        Overall device revision identifier. Format of string is
        manufacturer-specific. Readonly. May be changed by proprietery
        functions of firmware upload processes.

        This property has id ``3.14``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocadevicemanager_getocaversion:

    .. cpp:function:: OcaStatus GetOcaVersion(OcaUint16 &OcaVersion)

        Gets the value of the OcaVersion property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.1``.

        :param OcaUint16 OcaVersion: Output parameter.

    .. _ocadevicemanager_getmodelguid:

    .. cpp:function:: OcaStatus GetModelGUID(OcaModelGUID &GUID)

        Gets the model GUID. The return value indicates whether the GUID was
        successfully retrieved.

        This method has id ``3.2``.

        :param OcaModelGUID GUID: Output parameter.

    .. _ocadevicemanager_getserialnumber:

    .. cpp:function:: OcaStatus GetSerialNumber(OcaString &serialNumber)

        Gets the value of the SerialNumber property. The return value
        indicates whether the property was successfully retrieved.

        This method has id ``3.3``.

        :param OcaString serialNumber: Output parameter.

    .. _ocadevicemanager_getdevicename:

    .. cpp:function:: OcaStatus GetDeviceName(OcaString &Name)

        Gets the device name. The return value indicates whether the property
        was successfully retrieved.

        This method has id ``3.4``.

        :param OcaString Name: Output parameter.

    .. _ocadevicemanager_setdevicename:

    .. cpp:function:: OcaStatus SetDeviceName(OcaString Name)

        Sets the device name. The return value indicates whether the property
        was successfully set.

        This method has id ``3.5``.

        :param OcaString Name: Input parameter.

    .. _ocadevicemanager_getmodeldescription:

    .. cpp:function:: OcaStatus GetModelDescription(OcaModelDescription &Description)

        Gets the model description. The return value indicates whether the
        description was successfully retrieved.

        This method has id ``3.6``.

        :param OcaModelDescription Description: Output parameter.

    .. _ocadevicemanager_getdevicerole:

    .. cpp:function:: OcaStatus GetDeviceRole(OcaString &role)

        Gets the value of the Role property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.7``.

        :param OcaString role: Output parameter.

    .. _ocadevicemanager_setdevicerole:

    .. cpp:function:: OcaStatus SetDeviceRole(OcaString role)

        Sets the value of the Role property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.8``.

        :param OcaString role: Input parameter.

    .. _ocadevicemanager_getuserinventorycode:

    .. cpp:function:: OcaStatus GetUserInventoryCode(OcaString &Code)

        Gets the value of the UserInventoryCode property. The return value
        indicates whether the property was successfully retrieved.

        This method has id ``3.9``.

        :param OcaString Code: Output parameter.

    .. _ocadevicemanager_setuserinventorycode:

    .. cpp:function:: OcaStatus SetUserInventoryCode(OcaString Code)

        Sets the value of the UserInventoryCode property. The return value
        indicates whether the property was successfully set.

        This method has id ``3.10``.

        :param OcaString Code: Input parameter.

    .. _ocadevicemanager_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        Gets the value of the Enabled property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.11``.

        :param OcaBoolean enabled: Output parameter.

    .. _ocadevicemanager_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        Sets the value of the Enabled property. The return value indicates
        whether the property was successfully set.

        This method has id ``3.12``.

        :param OcaBoolean enabled: Input parameter.

    .. _ocadevicemanager_getstate:

    .. cpp:function:: OcaStatus GetState(OcaDeviceState &state)

        Gets the value of the State property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.13``.

        :param OcaDeviceState state: Output parameter.

    .. _ocadevicemanager_setresetkey:

    .. cpp:function:: OcaStatus SetResetKey(OcaBlobFixedLen<16> Key, OcaNetworkAddress Address)

        Sets the value of the reset key of the device. The return value
        indicates whether the property was successfully set. Note that the
        device manager must inform the CAP gateway of this key (via the host
        interface), since the CAP gateway will check for and handle the
        special reset message.

        This method has id ``3.14``.

        :param OcaBlobFixedLen<16> Key: Input parameter.
        :param OcaNetworkAddress Address: Input parameter.

    .. _ocadevicemanager_getresetcause:

    .. cpp:function:: OcaStatus GetResetCause(OcaResetCause &resetCause)

        Gets the value of the ResetCause property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``3.15``.

        :param OcaResetCause resetCause: Output parameter.

    .. _ocadevicemanager_clearresetcause:

    .. cpp:function:: OcaStatus ClearResetCause()

        Clears the ResetCause property, i.e. resets it to the default value
        'PowerOn'. Must be used after the reset cause has been read out to
        ensure differentation between reconnects due to network loss and
        reconnects due to external or internal reset. Offered as a separate
        method (instead of implicitly clearing the cause after it has been
        read out) to accomodate systems that have multiple controllers. The
        return value indicates whether the property was successfully
        retrieved.

        This method has id ``3.16``.


    .. _ocadevicemanager_getmessage:

    .. cpp:function:: OcaStatus GetMessage(OcaString &Message)

        Gets the value of property **Message** . Return value indicates
        whether value was successfully retrieved.

        This method has id ``3.17``.

        :param OcaString Message: Output parameter.

    .. _ocadevicemanager_setmessage:

    .. cpp:function:: OcaStatus SetMessage(OcaString Text)

        Set arbitrary text message into **Message** property. The return value
        indicates whether the value was successfully set.

        This method has id ``3.18``.

        :param OcaString Text: Input parameter.

    .. _ocadevicemanager_getmanagers:

    .. cpp:function:: OcaStatus GetManagers(OcaList<OcaManagerDescriptor> &Managers)

        Retrive the list of descriptors of managers instantiated in this
        device. The return value indicates whether the retrieval was
        successful.

        This method has id ``3.19``.

        :param OcaList<OcaManagerDescriptor> Managers: Output parameter.

    .. _ocadevicemanager_getdevicerevisionid:

    .. cpp:function:: OcaStatus GetDeviceRevisionID(OcaString &ID)

        Gets the value of property **DeviceRevisionID** . Return value
        indicates whether value was successfully retrieved.

        This method has id ``3.20``.

        :param OcaString ID: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
