*****************************
Network Application Datatypes
*****************************

.. _OcaNetworkAdvertisingService:

OcaNetworkAdvertisingService
============================

.. cpp:enum:: OcaNetworkAdvertisingService : uint8_t

    Network advertising services.

    .. cpp:enumerator:: DNSSD = 0

        Network Advertisement service DNS-SD [RFC 6763]

    .. cpp:enumerator:: MDNS_DNSSD = 1

        Network Advertisement service mDNS [RFC 6762] + DNS-SD [RFC 6763]

    .. cpp:enumerator:: NMOS = 2

        Network Advertisement service defined by AMWA NMOS. {NMOS-IS-04}

    .. cpp:enumerator:: ExpansionBase = 128

        Proprietary additions start here.

.. _OcaNetworkAdvertisingMechanism:

OcaNetworkAdvertisingMechanism
==============================

.. cpp:struct:: OcaNetworkAdvertisingMechanism

    Descriptor of a Network Advertising mechanism specified by a Network
    Assignment.

    .. cpp:member:: OcaNetworkAdvertisingService Service

        Advertising service used

    .. cpp:member:: OcaParameterRecord Parameters

        Advertising parameters. Content depends on advertising service used.

.. _OcaNetworkInterfaceAssignment:

OcaNetworkInterfaceAssignment
=============================

.. cpp:struct:: OcaNetworkInterfaceAssignment

    Assignment of a Network Interface object to a Network Application object.
    Also specifies associated Network Advertising mechanism(s).

    .. cpp:member:: OcaID16 ID

        Internal ID of Network Assignment. Unique within the instance of
        **OcaMediaTransportApplication** (or subclass)**** that owns the
        Assignment.

    .. cpp:member:: OcaONo NetworkInterfaceONo

        ONo of the Network Interface

    .. cpp:member:: OcaAdaptationData NetworkBindingParameters

        Assignment-specific parameters. Format depends on application. For
        example, IP-based applications can use this field to designate the IP
        port being used.

    .. cpp:member:: OcaList<OcaString> SecurityKeyIdentities

        List of identities of security keys that apply to this assignment.
        Assumes the identities refer to private shared keys registered in
        **OcaSecurityManager**.

    .. cpp:member:: OcaList<OcaNetworkAdvertisingMechanism> AdvertisingMechanisms

        List of advertising mechanisms associated with this Assignment. May be
        empty.

