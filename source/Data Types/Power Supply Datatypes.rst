**********************
Power Supply Datatypes
**********************

.. _OcaPowerSupplyType:

OcaPowerSupplyType
==================

.. cpp:enum:: OcaPowerSupplyType : uint8_t

    Type of power supply.

    .. cpp:enumerator:: None = 0

        No power supply.

    .. cpp:enumerator:: Mains = 1

        Mains-powered power supply.

    .. cpp:enumerator:: Battery = 2

        Battery power supply.

    .. cpp:enumerator:: Phantom = 3

        Phantom power supply. Includes Power-over-Ethernet supplies.

    .. cpp:enumerator:: Solar = 4

        Solar power supply

.. _OcaPowerSupplyLocation:

OcaPowerSupplyLocation
======================

.. cpp:enum:: OcaPowerSupplyLocation : uint8_t

    Physical location of a device power supply.

    .. cpp:enumerator:: Unspecified = 1

        Unspecified location

    .. cpp:enumerator:: Internal = 2

        Power supply is physically inside the device.

    .. cpp:enumerator:: External = 3

        Power supply is physically outside the device.

.. _OcaPowerSupplyState:

OcaPowerSupplyState
===================

.. cpp:enum:: OcaPowerSupplyState : uint8_t

    State of a power supply.

    .. cpp:enumerator:: Off = 0

        Powered down.

    .. cpp:enumerator:: Unavailable = 1

        Power supply is turned on but not available for activation.

    .. cpp:enumerator:: Available = 2

        Power supply is fully available for activation.

    .. cpp:enumerator:: Active = 3

        Power supply is currently supplying power to the device.

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

