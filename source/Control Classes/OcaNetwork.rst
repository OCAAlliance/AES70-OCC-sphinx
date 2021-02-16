.. _ocanetwork:

1.2.1  OcaNetwork
=================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaNetwork: OcaAgent

    **DEPRECATED CLASS** *Replaced by class* **OcaControlNetwork ** *in
    version 3 of Connection Management (CM3)* Abstract base class for
    defining network classes to which this device belongs. This class is
    to be used for control and monitoring networks only. For media
    transport networks, and for networks that combine media transport and
    control, the **OcaStreamNetwork** class should be used instead.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaNetworkLinkType LinkType

        This property has id ``3.0``.

        Network link type - e.g. wired Ethernet, USB, ... See the
        OcaNetworkType enum for details. This is a read-only property whose
        value is fixed to the class that is inherited from OcaNetwork to
        implement each specific type of network.

    .. cpp:member:: OcaApplicationNetworkServiceID IDAdvertised

        This property has id ``3.0``.

        ID by which this network object is known on the network, i.e. the name
        or GUID that this network object publishes in the network's
        directory/discovery system. As of OCA 1.4, this description has been
        clarified to indicate this property is the registered service name,
        which may or may not be the same as the device's host name, if any.
        For data network types that have host names (e.g. IP networks), the
        authoritative copy of the host name is in the system interface ID.

    .. cpp:member:: OcaNetworkControlProtocol ControlProtocol

        This property has id ``3.0``.

        Type of control protocol used by the network (OCAnn) or NONE if this
        network is not used for control.

    .. cpp:member:: OcaNetworkMediaProtocol MediaProtocol

        This property has id ``3.0``.

        Deprecated property. Always has value NONE. Media transport is managed
        by the **OcaStreamNetwork** class.

    .. cpp:member:: OcaNetworkStatus Status

        This property has id ``3.0``.

        Operational status of the network.

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceID> SystemInterfaces

        This property has id ``3.0``.

        Collection of identifiers of system interface(s) used by the network.
        A "system interface" is the system service through which network
        traffic passes into and out of the device -- e.g. a socket. The
        identifier format is system and network dependent; for OCA purposes,
        it is maintained as a variable-length blob which the protocol does not
        inspect.

    .. cpp:member:: OcaList<OcaONo> MediaPorts

        This property has id ``3.0``.

        Deprecated property. Always is empty. Media transport is now managed
        by the class **OcaStreamNetwork.**

    .. cpp:member:: OcaNetworkStatistics Statistics

        This property has id ``3.0``.

        Error statistics for this network

    .. cpp:function:: OcaStatus GetLinkType(OcaNetworkLinkType &Type)

        This method has id ``3.1``.

        Gets the network's link type (wired Ethernet, USB, etc.). Return
        status indicates whether the operation was successful.

        :param OcaNetworkLinkType Type: Output parameter.

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaApplicationNetworkServiceID &Name)

        This method has id ``3.2``.

        Gets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaApplicationNetworkServiceID Name: Output parameter.

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaApplicationNetworkServiceID Name)

        This method has id ``3.3``.

        Sets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaApplicationNetworkServiceID Name: Input parameter.

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        This method has id ``3.4``.

        Gets the network's ControlProtocol property. Return status indicates
        whether the operation was successful.

        :param OcaNetworkControlProtocol Protocol: Output parameter.

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        This method has id ``3.5``.

        Gets the network's MediaProtocol property. This is a deprecated method
        that always returns the value NONE.

        :param OcaNetworkMediaProtocol Protocol: Output parameter.

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkStatus &Status)

        This method has id ``3.6``.

        Retrieves the network's status. Return status indicates whether the
        status was successfully retrieved.

        :param OcaNetworkStatus Status: Output parameter.

    .. cpp:function:: OcaStatus GetStatistics(OcaNetworkStatistics &Status)

        This method has id ``3.7``.

        Retrieves network error statistics counter values. Return status
        indicates whether the values were successfully retrieved.

        :param OcaNetworkStatistics Status: Output parameter.

    .. cpp:function:: OcaStatus ResetStatistics()

        This method has id ``3.8``.

        Resets network error statistics counters. Return status indicates
        whether the counters were successfully reset.


    .. cpp:function:: OcaStatus GetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> &Interfaces)

        This method has id ``3.9``.

        Gets the list of system interface IDs that this network is using.
        Return status indicates success of the operation.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Output parameter.

    .. cpp:function:: OcaStatus SetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceID> Interfaces)

        This method has id ``3.10``.

        Sets the list of system interface IDs that this network will use.
        Return status indicates success of the operation. This method is not
        implemented by all network implementations.

        :param OcaList<OcaNetworkSystemInterfaceID> Interfaces: Input parameter.

    .. cpp:function:: OcaStatus GetMediaPorts(OcaList<OcaONo> &Ports)

        This method has id ``3.11``.

        Deprecated method. Always returns status INVALID_REQUEST. Media
        transport is now managed by the class **OcaStreamNetwork.**

        :param OcaList<OcaONo> Ports: Output parameter.

    .. cpp:function:: OcaStatus Startup()

        This method has id ``3.12``.

        Start up this network.


    .. cpp:function:: OcaStatus Shutdown()

        This method has id ``3.13``.

        Shut down this network.


