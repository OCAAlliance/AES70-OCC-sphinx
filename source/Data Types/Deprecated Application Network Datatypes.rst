****************************************
Deprecated Application Network Datatypes
****************************************

.. _OcaApplicationNetworkServiceID:

OcaApplicationNetworkServiceID
==============================

.. cpp:type:: OcaApplicationNetworkServiceID = OcaBlob

    Generic host ID.

.. _OcaNetworkSystemInterfaceDescriptor:

OcaNetworkSystemInterfaceDescriptor
===================================

.. cpp:type:: OcaNetworkSystemInterfaceDescriptor = OcaBlob

    Descriptor of a system interface used by a network. Format is data network
    type dependent.

.. _OcaApplicationNetworkState:

OcaApplicationNetworkState
==========================

.. cpp:enum:: OcaApplicationNetworkState : uint8_t

    Network states.

    .. cpp:enumerator:: Unknown = 0

        State is not known.

    .. cpp:enumerator:: NotReady = 1

        Application network is not connected to host data network and is
        therefore not ready for connection establishng or application data
        transfer.

    .. cpp:enumerator:: Readying = 2

        Application network is in the process of connecting to the host data
        network and is therefore not ready for connection establishing or
        application data transfer.

.. _OcaApplicationNetworkCommand:

OcaApplicationNetworkCommand
============================

.. cpp:enum:: OcaApplicationNetworkCommand : uint8_t

    Command values for OcaMediaNetwork.Control().

    .. cpp:enumerator:: None = 0

        No-op. State is not changed.

    .. cpp:enumerator:: Prepare = 1

        Open a connection to the host data network, but do not make any media
        connections. Resulting state = Ready.

    .. cpp:enumerator:: Start = 2

        Commence media data connection-making and data transfer. Resulting state
        = Running.

