*******************************
Deprecated Management Datatypes
*******************************

.. _OcaDeviceState:

OcaDeviceState
==============

.. cpp:type:: OcaDeviceState = OcaBitSet16

    Bitset defining bit flags that indicate the device states AES70 devices can
    be in. The state is returned by the device's Device Manager on request. Any
    combination of the flags may be returned, unless specified otherwise for the
    specific flag. The value 0x0000 indicates the device is fully operational.

.. _OcaModelGUID:

OcaModelGUID
============

.. cpp:struct:: OcaModelGUID


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

