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


OCP.1 Encoding
--------------

================== ========== ==========================
Field              Basic type Byte length               
================== ========== ==========================
ObjectNumber.ONo   OcaUint32  4                         
Name.Len           OcaUint16  2                         
Name.Value         string     variable                  
ClassID            OcaClassID (2 + Count * 2 * variable)
ClassVersion.Value OcaUint16  2                         
================== ========== ==========================


.. _OcaManagerDefaultObjectNumbers:

OcaManagerDefaultObjectNumbers
==============================

.. cpp:struct:: OcaManagerDefaultObjectNumbers
    
    Datatype that defines the fixed object numbers assigned to the various
    **OcaManager** objects.

    .. cpp:member:: OcaONo DeviceManager


    .. cpp:member:: OcaONo SecurityManager


    .. cpp:member:: OcaONo FirmwareManager


    .. cpp:member:: OcaONo SubscriptionManager


    .. cpp:member:: OcaONo PowerManager


    .. cpp:member:: OcaONo NetworkManager


    .. cpp:member:: OcaONo MediaClockManager


    .. cpp:member:: OcaONo LibraryManager


    .. cpp:member:: OcaONo AudioProcessingManager


    .. cpp:member:: OcaONo DeviceTimeManager


    .. cpp:member:: OcaONo TaskManager


    .. cpp:member:: OcaONo CodingManager


    .. cpp:member:: OcaONo DiagnosticManager



OCP.1 Encoding
--------------

========================== ========== ===========
Field                      Basic type Byte length
========================== ========== ===========
DeviceManager.ONo          OcaUint32  4          
SecurityManager.ONo        OcaUint32  4          
FirmwareManager.ONo        OcaUint32  4          
SubscriptionManager.ONo    OcaUint32  4          
PowerManager.ONo           OcaUint32  4          
NetworkManager.ONo         OcaUint32  4          
MediaClockManager.ONo      OcaUint32  4          
LibraryManager.ONo         OcaUint32  4          
AudioProcessingManager.ONo OcaUint32  4          
DeviceTimeManager.ONo      OcaUint32  4          
TaskManager.ONo            OcaUint32  4          
CodingManager.ONo          OcaUint32  4          
DiagnosticManager.ONo      OcaUint32  4          
========================== ========== ===========


.. _OcaDeviceState:

OcaDeviceState
==============

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

        Model code. Unique within the given manufacturer's products. May be
        set freely by the manufacturer.


OCP.1 Encoding
--------------

========= ================== ===========
Field     Basic type         Byte length
========= ================== ===========
Reserved  OcaBlobFixedLen<1> 1          
MfrCode   OcaBlobFixedLen<3> 3          
ModelCode OcaBlobFixedLen<4> 4          
========= ================== ===========


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


OCP.1 Encoding
--------------

================== ========== ===========
Field              Basic type Byte length
================== ========== ===========
Manufacturer.Len   OcaUint16  2          
Manufacturer.Value string     variable   
Name.Len           OcaUint16  2          
Name.Value         string     variable   
Version.Len        OcaUint16  2          
Version.Value      string     variable   
================== ========== ===========


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

        Reset due to an external request (i.e. Reset method of DeviceManager
        or hardware reset pin).
.. _OcaComponent:

OcaComponent
============

.. cpp:enum:: OcaComponent : uint16_t

    Enumeration (16-bit) for of software :raw:html:`&amp;` firmware
    components in the device. Except for the boot loader, all other values
    of this enum are device-specific and will be specified by subclassing
    this class.

    .. cpp:enumerator:: BootLoader = 0

        The boot loader image.
.. _OcaPowerState:

OcaPowerState
=============

.. cpp:enum:: OcaPowerState : uint8_t

    Enumeration defining the power states that OCA devices can be in. The
    state is returned by the device's Power Manager on request.

    .. cpp:enumerator:: None = 0

        Unspecified state.
    .. cpp:enumerator:: Working = 1

        Power is on.
    .. cpp:enumerator:: Standby = 2

        The device is in standby mode, but may be awoken by a call to the
        appropriate state-changing method of this class.
    .. cpp:enumerator:: Off = 3

        The device is off, but may (depending on implementation) be awoken by
        a transport-dependent wakeup mechanism.