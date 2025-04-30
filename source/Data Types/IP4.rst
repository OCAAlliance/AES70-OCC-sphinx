***
IP4
***

.. _OcaIP4Address:

OcaIP4Address
=============

.. cpp:type:: OcaIP4Address = OcaString

    IP version 4 network address in string form "x1.x2.x3.x4" where the x's are
    decimal integers in the range 0...255.

.. _OcaIP4AddressAndPrefix:

OcaIP4AddressAndPrefix
======================

.. cpp:type:: OcaIP4AddressAndPrefix = OcaString

    IP version4 address prefix in string form "x1.x2.x3.x4/n" where the x's are
    decimal integers in the range 0...255, and n is an integer in the range
    0...31. n specifies the number of bits occupied by the prefix. This
    construct replaces the conventional IPv4 address + subnet mask. Examples
    123.456.789.001 / 16 = 123.456.789.001 + 255.255.0.0 123.456.789.001 / 24 =
    123.456.789.001 + 255.255.255.0

.. _OcaIP4Gateway:

OcaIP4Gateway
=============

.. cpp:struct:: OcaIP4Gateway

    Descriptor of an IPV4 gateway

    .. cpp:member:: OcaIP4AddressAndPrefix DestinationPrefix

        Prefix of destinations to which this gateway provides access.

    .. cpp:member:: OcaIP4Address GatewayAddress

        Address of this gateway

    .. cpp:member:: OcaUint16 Metric

        Cost of using this gateway. 0=lowest.

.. _OcaIP4AutoconfigMode:

OcaIP4AutoconfigMode
====================

.. cpp:enum:: OcaIP4AutoconfigMode : uint8_t

    Autoconfiguration mode

    .. cpp:enumerator:: None = 0

        No autoconfig - manual address entry

    .. cpp:enumerator:: DHCP = 1

        DHCP

    .. cpp:enumerator:: DHCP_LINKLOCAL = 2

        DHCP with link-local fallback

    .. cpp:enumerator:: LINKLOCAL = 3

        Link-local only

.. _OcaIP4NetworkSettings:

OcaIP4NetworkSettings
=====================

.. cpp:struct:: OcaIP4NetworkSettings

    IPv4 parameters for **OcaNetworkInterface. ** Stored in the**
    .CurrentNetworkSettings** and **.TargetNetworkSettings** properties.

    .. cpp:member:: OcaIP4AddressAndPrefix AddressAndPrefix

        Network address and prefix of this interface

    .. cpp:member:: OcaIP4AutoconfigMode AutoconfigMode

        See **OcaIP4AutoconfigMode** definition.

    .. cpp:member:: OcaIP4Address DhcpServerAddress

        DHCP server address

    .. cpp:member:: OcaIP4Address DefaultGatewayAddress

        Address of default gateway. 0.0.0.0 means there is none.

    .. cpp:member:: OcaList<OcaIP4Gateway> AdditionalGateways

        Descriptor(s) of specific gateway(s). May be empty.

    .. cpp:member:: OcaList<OcaIP4Address> DnsServerAddresses

        DNS server address(es)

    .. cpp:member:: OcaParameterRecord AdditionalParameters

        Additional connection parameters, if any.

