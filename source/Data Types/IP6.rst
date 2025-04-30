***
IP6
***

.. _OcaIP6Address:

OcaIP6Address
=============

.. cpp:type:: OcaIP6Address = OcaString

    IPv6 network address in string form, per [RFC 2373]

.. _OcaIP6AddressAndPrefix:

OcaIP6AddressAndPrefix
======================

.. cpp:type:: OcaIP6AddressAndPrefix = OcaString

    IPv6 network address with prefix length designator, per [RFC 2373]. Example:
    1234:5678:0001::/64

.. _OcaIP6AutoconfigMode:

OcaIP6AutoconfigMode
====================

.. cpp:enum:: OcaIP6AutoconfigMode : uint8_t

    Autoconfiguration mode

    .. cpp:enumerator:: NONE = 0

        No autoconfig - manual address entry

    .. cpp:enumerator:: SLAAC = 1

        **S**tateless** A**uto **A**ddress **C**onfiguration. Address = prefix
        || mac-addr; mac-addr is MAC address in IEEE EUI-64 format. See [RFC
        3315].

    .. cpp:enumerator:: DHCP_STATELESS = 2

        Use SLAAC for address; DHCPv6 server provides ancillary info

    .. cpp:enumerator:: DHCP_STATEFUL = 3

        Use a DHCPv6 server for both address and ancillary info.

.. _OcaIP6Gateway:

OcaIP6Gateway
=============

.. cpp:struct:: OcaIP6Gateway

    Descriptor of an IPV6 gateway

    .. cpp:member:: OcaIP6AddressAndPrefix DestinationPrefix

        Prefix of destinations to which this gateway provides access.

    .. cpp:member:: OcaIP6Address GatewayAddress

        Address of this gateway

    .. cpp:member:: OcaUint16 Metric

        Cost of using this gateway. 0=lowest.

.. _OcaIP6NetworkSettings:

OcaIP6NetworkSettings
=====================

.. cpp:struct:: OcaIP6NetworkSettings

    IPv4 parameters for **OcaNetworkInterface.AdaptationData**

    .. cpp:member:: OcaIP6AddressAndPrefix AddressAndPrefix

        Current interface address including prefix len

    .. cpp:member:: OcaIP6AutoconfigMode AutoconfigMode

        {NONE, SLAAC, DHCP_STATELESS, DHCP_STATEFUL}

    .. cpp:member:: OcaIP6Address LinkLocalAddress

        Link-local address

    .. cpp:member:: OcaIP6Address DhcpServerAddress

        Network address

    .. cpp:member:: OcaIP6Address DefaultGatewayAddress

        Network address

    .. cpp:member:: OcaList<OcaIP6Gateway> AdditionalGateways

        Gateway descriptor(s)

    .. cpp:member:: OcaList<OcaIP6Address> DnsServerAddresses

        DNS server address(es)

    .. cpp:member:: OcaParameterRecord AdditionalParameters

        Additional connection parameters, if any.

