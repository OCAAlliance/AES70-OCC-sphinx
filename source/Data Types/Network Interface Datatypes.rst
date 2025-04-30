***************************
Network Interface Datatypes
***************************

.. _OcaNetworkInterfaceState:

OcaNetworkInterfaceState
========================

.. cpp:enum:: OcaNetworkInterfaceState : uint8_t

    Network Interface state.

    .. cpp:enumerator:: NotReady = 0

        Network interface is not ready for data transfer.

    .. cpp:enumerator:: Ready = 1

        Network interface is ready for data transfer.

    .. cpp:enumerator:: Fault = 2

        Network interface has ceased all activity due to an error.

.. _OcaNetworkInterfaceStatus:

OcaNetworkInterfaceStatus
=========================

.. cpp:struct:: OcaNetworkInterfaceStatus

    Network-type-specific network interface status.

    .. cpp:member:: OcaNetworkInterfaceState State

        Generic state of the network interface

    .. cpp:member:: OcaAdaptationData AdaptationData

        Adaptation-dependent state data

.. _OcaNetworkInterfaceCommand:

OcaNetworkInterfaceCommand
==========================

.. cpp:enum:: OcaNetworkInterfaceCommand : uint8_t

    Command values for **OcaNetworkInterface.ApplyCommand().**

    .. cpp:enumerator:: Start = 0

        If **State** is **NotReady** or **Fault:** applies
        **TargetNetworkSettings** ** ** sets **NetworkSettingsPending** to
        **FALSE** sets **State** to **Ready** ** ** commences network I/O. else
        does nothing.

    .. cpp:enumerator:: Stop = 1

        Ceases network I/O and sets **State** to **NotReady.**

    .. cpp:enumerator:: Restart = 2

        Performs a **Stop** command,. After **State** becomes **NotReady**,
        performs a **Start** command.

