********************
Management Datatypes
********************

.. _OcaManagerDescriptor:

OcaManagerDescriptor
====================

.. cpp:struct:: OcaManagerDescriptor

    Structure that describes a manager instance.

    .. cpp:member:: OcaONo ObjectNumber

        Object number of this manager instance.

    .. cpp:member:: OcaString Name

        Name of the manager instance.

    .. cpp:member:: OcaClassID ClassID

        ClassID of the class from which the manager instance was created.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Version number of the class from which this instance was created.

.. _OcaManagerDefaultObjectNumbers:

OcaManagerDefaultObjectNumbers
==============================

.. cpp:enum:: OcaManagerDefaultObjectNumbers

    Datatype that defines the fixed object numbers assigned to the various
    **OcaManager** objects.

    .. cpp:enumerator:: DeviceManager = 1


    .. cpp:enumerator:: SecurityManager = 2


    .. cpp:enumerator:: FirmwareManager = 3


    .. cpp:enumerator:: SubscriptionManager = 4


    .. cpp:enumerator:: PowerManager = 5


    .. cpp:enumerator:: NetworkManager = 6


    .. cpp:enumerator:: MediaClockManager = 7


    .. cpp:enumerator:: LibraryManager = 8


    .. cpp:enumerator:: AudioProcessingManager = 9


    .. cpp:enumerator:: DeviceTimeManager = 10


    .. cpp:enumerator:: TaskManager = 11


    .. cpp:enumerator:: CodingManager = 12


    .. cpp:enumerator:: DiagnosticManager = 13


.. _OcaDeviceState:

OcaDeviceState
==============

.. cpp:type:: OcaDeviceState = OcaBitSet16

    Bitset defining bit flags that indicate the device states CAP devices can be
    in. The state is returned by the device's Device Manager on request. Any
    combination of the flags may be returned, unless specified otherwise for the
    specific flag. The value 0x0000 indicates the device is fully operational.

.. _OcaModelGUID:

OcaModelGUID
============

.. cpp:struct:: OcaModelGUID

    64 bit device type GUID.

    .. cpp:member:: OcaBlobFixedLen<1> Reserved

        8 reserved bits.

    .. cpp:member:: OcaBlobFixedLen<3> MfrCode

        IEEE Manufacturer code. Unique worldwide.

    .. cpp:member:: OcaBlobFixedLen<4> ModelCode

        Model code. Unique within the given manufacturer's products. May be set
        freely by the manufacturer.

.. _OcaModelDescription:

OcaModelDescription
===================

.. cpp:struct:: OcaModelDescription

    Friendly description of this particular product model.

    .. cpp:member:: OcaString Manufacturer

        Name of manufacturer.

    .. cpp:member:: OcaString Name

        Name of this model (whatever the manufacturer wants to call it).

    .. cpp:member:: OcaString Version

        Text name for the version of this model, e.g. "1.2.1a".

.. _OcaResetCause:

OcaResetCause
=============

.. cpp:enum:: OcaResetCause : uint8_t

    Enumeration of reasons for device reset.

    .. cpp:enumerator:: PowerOn = 0

        Reset due to powering up.

    .. cpp:enumerator:: InternalError = 1

        Reset due to internal error.

    .. cpp:enumerator:: Upgrade = 2

        Reset following upgrade of firmware.

    .. cpp:enumerator:: ExternalRequest = 3

        Reset due to an external request (i.e. Reset method of DeviceManager or
        hardware reset pin).

.. _OcaComponent:

OcaComponent
============

.. cpp:enum:: OcaComponent : uint16_t

    Enumeration (16-bit) for of software & firmware components in the device.
    Except for the boot loader, all other values of this enum are
    device-specific and will be specified by subclassing this class.

    .. cpp:enumerator:: BootLoader = 0

        The boot loader image.

.. _OcaPowerState:

OcaPowerState
=============

.. cpp:enum:: OcaPowerState : uint8_t

    Enumeration defining the power states that OCA devices can be in. The state
    is returned by the device's Power Manager on request.

    .. cpp:enumerator:: None = 0

        Unspecified state.

    .. cpp:enumerator:: Working = 1

        Power is on.

    .. cpp:enumerator:: Standby = 2

        The device is in standby mode, but may be awoken by a call to the
        appropriate state-changing method of this class.

    .. cpp:enumerator:: Off = 3

        The device is off, but may (depending on implementation) be awoken by a
        transport-dependent wakeup mechanism.

