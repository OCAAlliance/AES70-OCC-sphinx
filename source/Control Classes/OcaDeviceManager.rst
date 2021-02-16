.. _ocadevicemanager:

1.3.1  OcaDeviceManager
=======================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaDeviceManager: OcaManager

    Mandatory manager that contains information relevant to the whole
    device.
    
    - Must be instantiated once in every device.
    
    
    - Must have object number 1.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaModelGUID ModelGUID

        This property has id ``3.1``.

        Read-only property that identifies the model of the device. Note this
        property is not equivalent to a MAC address, because (a) MAC addresses
        identify individual devices, not models, and (b) MAC addresses are
        Ethernet-specific, but an OCA device need not have an Ethernet port.

    .. cpp:member:: OcaString SerialNumber

        This property has id ``3.2``.

        Read-only property that identifies the serial number of the CAP
        device.

    .. cpp:member:: OcaModelDescription ModelDescription

        This property has id ``3.3``.

        Read-only property that contains text names for this model, its
        manufacturer, and its version.

    .. cpp:member:: OcaString DeviceName

        This property has id ``3.4``.

        Name of the device. Should be unique manufacturer-qualified
        identifier.

    .. cpp:member:: OcaUint16 OcaVersion

        This property has id ``3.5``.

        Read-only property that indicates the AES70 version number used by the
        device.

    .. cpp:member:: OcaString DeviceRole

        This property has id ``3.6``.

        Role of device in application (arbitrary).

    .. cpp:member:: OcaString UserInventoryCode

        This property has id ``3.7``.

        Code used for equipment tracking.

    .. cpp:member:: OcaBoolean Enabled

        This property has id ``3.8``.

        Indicates whether the device is enabled (and therefore operational).

    .. cpp:member:: OcaDeviceState State

        This property has id ``3.9``.

        Read-only property that indicates the current state of the device.

    .. cpp:member:: OcaBoolean Busy

        This property has id ``3.10``.

        True iff device is working on something and is not available for OCA
        command activity. Readonly.

    .. cpp:member:: OcaResetCause ResetCause

        This property has id ``3.11``.

        Read-only attribute that indicates the reset cause of the last reset.

    .. cpp:member:: OcaString Message

        This property has id ``3.12``.

        Arbitrary text message provided by controller. Display and handling of
        the text is device-dependent and not defined by OCA.

    .. cpp:member:: OcaList<OcaManagerDescriptor> Managers

        This property has id ``3.13``.

        List of all manager objects instantiated in this device.

    .. cpp:member:: OcaString DeviceRevisionID

        This property has id ``3.14``.

        Overall device revision identifier. Format of string is
        manufacturer-specific. Readonly. May be changed by proprietery
        functions of firmware upload processes.

    .. cpp:function:: OcaStatus GetOcaVersion(OcaUint16 &OcaVersion)

        This method has id ``3.1``.

        Gets the value of the OcaVersion property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaUint16 OcaVersion: Output parameter.

    .. cpp:function:: OcaStatus GetModelGUID(OcaModelGUID &GUID)

        This method has id ``3.2``.

        Gets the model GUID. The return value indicates whether the GUID was
        successfully retrieved.

        :param OcaModelGUID GUID: Output parameter.

    .. cpp:function:: OcaStatus GetSerialNumber(OcaString &serialNumber)

        This method has id ``3.3``.

        Gets the value of the SerialNumber property. The return value
        indicates whether the property was successfully retrieved.

        :param OcaString serialNumber: Output parameter.

    .. cpp:function:: OcaStatus GetDeviceName(OcaString &Name)

        This method has id ``3.4``.

        Gets the device name. The return value indicates whether the property
        was successfully retrieved.

        :param OcaString Name: Output parameter.

    .. cpp:function:: OcaStatus SetDeviceName(OcaString Name)

        This method has id ``3.5``.

        Sets the device name. The return value indicates whether the property
        was successfully set.

        :param OcaString Name: Input parameter.

    .. cpp:function:: OcaStatus GetModelDescription(OcaModelDescription &Description)

        This method has id ``3.6``.

        Gets the model description. The return value indicates whether the
        description was successfully retrieved.

        :param OcaModelDescription Description: Output parameter.

    .. cpp:function:: OcaStatus GetDeviceRole(OcaString &role)

        This method has id ``3.7``.

        Gets the value of the Role property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaString role: Output parameter.

    .. cpp:function:: OcaStatus SetDeviceRole(OcaString role)

        This method has id ``3.8``.

        Sets the value of the Role property. The return value indicates
        whether the property was successfully set.

        :param OcaString role: Input parameter.

    .. cpp:function:: OcaStatus GetUserInventoryCode(OcaString &Code)

        This method has id ``3.9``.

        Gets the value of the UserInventoryCode property. The return value
        indicates whether the property was successfully retrieved.

        :param OcaString Code: Output parameter.

    .. cpp:function:: OcaStatus SetUserInventoryCode(OcaString Code)

        This method has id ``3.10``.

        Sets the value of the UserInventoryCode property. The return value
        indicates whether the property was successfully set.

        :param OcaString Code: Input parameter.

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        This method has id ``3.11``.

        Gets the value of the Enabled property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean enabled: Output parameter.

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        This method has id ``3.12``.

        Sets the value of the Enabled property. The return value indicates
        whether the property was successfully set.

        :param OcaBoolean enabled: Input parameter.

    .. cpp:function:: OcaStatus GetState(OcaDeviceState &state)

        This method has id ``3.13``.

        Gets the value of the State property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaDeviceState state: Output parameter.

    .. cpp:function:: OcaStatus SetResetKey(OcaBlobFixedLen<16> Key, OcaNetworkAddress Address)

        This method has id ``3.14``.

        Sets the value of the reset key of the device. The return value
        indicates whether the property was successfully set. Note that the
        device manager must inform the CAP gateway of this key (via the host
        interface), since the CAP gateway will check for and handle the
        special reset message.

        :param OcaBlobFixedLen<16> Key: Input parameter.
        :param OcaNetworkAddress Address: Input parameter.

    .. cpp:function:: OcaStatus GetResetCause(OcaResetCause &resetCause)

        This method has id ``3.15``.

        Gets the value of the ResetCause property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaResetCause resetCause: Output parameter.

    .. cpp:function:: OcaStatus ClearResetCause()

        This method has id ``3.16``.

        Clears the ResetCause property, i.e. resets it to the default value
        'PowerOn'. Must be used after the reset cause has been read out to
        ensure differentation between reconnects due to network loss and
        reconnects due to external or internal reset. Offered as a separate
        method (instead of implicitly clearing the cause after it has been
        read out) to accomodate systems that have multiple controllers. The
        return value indicates whether the property was successfully
        retrieved.


    .. cpp:function:: OcaStatus GetMessage(OcaString &Message)

        This method has id ``3.17``.

        Gets the value of property **Message** . Return value indicates
        whether value was successfully retrieved.

        :param OcaString Message: Output parameter.

    .. cpp:function:: OcaStatus SetMessage(OcaString Text)

        This method has id ``3.18``.

        Set arbitrary text message into **Message** property. The return value
        indicates whether the value was successfully set.

        :param OcaString Text: Input parameter.

    .. cpp:function:: OcaStatus GetManagers(OcaList<OcaManagerDescriptor> &Managers)

        This method has id ``3.19``.

        Retrive the list of descriptors of managers instantiated in this
        device. The return value indicates whether the retrieval was
        successful.

        :param OcaList<OcaManagerDescriptor> Managers: Output parameter.

    .. cpp:function:: OcaStatus GetDeviceRevisionID(OcaString &ID)

        This method has id ``3.20``.

        Gets the value of property **DeviceRevisionID** . Return value
        indicates whether value was successfully retrieved.

        :param OcaString ID: Output parameter.

