********************
Management Datatypes
********************

.. _OcaManagerDescriptor:

OcaManagerDescriptor
====================

.. cpp:struct:: OcaManagerDescriptor

    Structure that describes a Manager instance.

    .. cpp:member:: OcaONo ObjectNumber

        Object number of this Manager instance.

    .. cpp:member:: OcaString Name

        Name of this Manager instance.

    .. cpp:member:: OcaClassID ClassID

        ClassID of the class from which the Manager instance was constructed.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Version number of the class from which this Manager instance was
        constructed.

.. _OcaManufacturer:

OcaManufacturer
===============

.. cpp:struct:: OcaManufacturer

    Structure that describes a manufacturer.

    .. cpp:member:: OcaString Name

        Manufacturer's name

    .. cpp:member:: OcaOrganizationID OrganizationID

        Manufacturer's IEEE OUI or CID, if any. Zero value means OUI or CID is
        not specified.

    .. cpp:member:: OcaString Website

        URL of the manufacturer's website. If none, an empty string shall be
        provided.

    .. cpp:member:: OcaString BusinessContact

        Contact information for business issues. If none, an empty string shall
        be provided.

    .. cpp:member:: OcaString TechnicalContact

        Contact information for technical issues. If none, an empty string shall
        be provided.

.. _OcaProduct:

OcaProduct
==========

.. cpp:struct:: OcaProduct

    Structure that describes a Product.

    .. cpp:member:: OcaString Name

        Product name

    .. cpp:member:: OcaString ModelID

        Manufacturer's unique model identifier.

    .. cpp:member:: OcaString RevisionLevel

        Manufacturer's product revision level code

    .. cpp:member:: OcaString BrandName

        Brand name under which product is sold

    .. cpp:member:: OcaUUID UUID

        Unique UUID of product. Not manufacturer-specific.

    .. cpp:member:: OcaString Description

        Text description of product

.. _OcaManagerDefaultObjectNumbers:

OcaManagerDefaultObjectNumbers
==============================

.. cpp:enum:: OcaManagerDefaultObjectNumbers

    Datatype that defines the fixed object numbers assigned to the various
    **OcaManager** objects.

    .. cpp:enumerator:: DeviceManager = 1

        Required

    .. cpp:enumerator:: SecurityManager = 2

        Optional

    .. cpp:enumerator:: FirmwareManager = 3

        Optional

    .. cpp:enumerator:: SubscriptionManager = 4

        Required

    .. cpp:enumerator:: PowerManager = 5

        Optional

    .. cpp:enumerator:: NetworkManager = 6

        Required if Device has **OcaNetworkInterface** and/or
        **OcaNetworkApplication** objects, or subclasses of them

    .. cpp:enumerator:: MediaClockManager = 7

        Required if device supports AES70-controlled media transport

    .. cpp:enumerator:: LibraryManager = 8

        Deprecated in OCA 1.5

    .. cpp:enumerator:: AudioProcessingManager = 9

        Optional

    .. cpp:enumerator:: DeviceTimeManager = 10

        Required if device knows what time it is

    .. cpp:enumerator:: TaskManager = 11

        Deprecated in OCA 1.5

    .. cpp:enumerator:: CodingManager = 12

        Deprecated in OCA 1.5

    .. cpp:enumerator:: DiagnosticManager = 13

        Optional

    .. cpp:enumerator:: LockManager = 14

        Optional

.. _OcaDeviceGenericState:

OcaDeviceGenericState
=====================

.. cpp:enum:: OcaDeviceGenericState : uint8_t

    Generic device states

    .. cpp:enumerator:: NormalOperation = 0

        Device is operating normally.

    .. cpp:enumerator:: Initializaing = 1

        Device is starting or restarting.

    .. cpp:enumerator:: Updating = 2

        Device is installing firmware.

    .. cpp:enumerator:: Fault = 3

        Device has encountered a terminal error and cannot continue to operate
        normally without external intervention.

    .. cpp:enumerator:: ExpansionBase = 128

        Base value for proprietary extensions

.. _OcaDeviceOperationalState:

OcaDeviceOperationalState
=========================

.. cpp:struct:: OcaDeviceOperationalState

    Operating state of device: generic state + device-specific details

    .. cpp:member:: OcaDeviceGenericState Generic

        Generic device state

    .. cpp:member:: OcaBlob Details

        Device-specific state details (optional)

.. _OcaComponent:

OcaComponent
============

.. cpp:enum:: OcaComponent : uint16_t

    Enumeration (16-bit) for of software & firmware components in the device.
    Except for the boot loader, all other values of this enum are
    device-specific and will be specified by subclassing this class.

    .. cpp:enumerator:: BootLoader = 0

        The boot loader image.

.. _OcaVersion:

OcaVersion
==========

.. cpp:struct:: OcaVersion

    Representation of a version number of a (hardware/software) component of a
    device in the form of Major.Minor.Build (e.g. 1.0.123).

    .. cpp:member:: OcaUint32 Major

        The major version number.

    .. cpp:member:: OcaUint32 Minor

        The minor version number.

    .. cpp:member:: OcaUint32 Build

        The build number. May be 0 if it is not used (e.g. for a hardware
        component).

    .. cpp:member:: OcaComponent Component

        The component.

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

    .. cpp:enumerator:: Unknown = 255


