.. _ocastreamnetwork:

1.2.10  OcaStreamNetwork
========================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaStreamNetwork: OcaAgent

    **DEPRECATED CLASS** *Replaced by class* **OcaMediaTransportNetwork **
    *in version 3 of Connection Management (CM3)* Abstract base class for
    defining network classes to which this device belongs. May be a media
    transport network, a control and monitoring network, or a network that
    does both. There shall be one OcaStreamNetwork instance for each
    network to which the device belongs. This class may be subclassed to
    support networks of various types.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaNetworkControlProtocol ControlProtocol

        This property has id ``3.0``.

        Type of control protocol used by the network (OCAnn) or NONE if this
        network is not used for control.

    .. cpp:member:: OcaNetworkNodeID IDAdvertised

        This property has id ``3.0``.

        ID by which this device is known on the network, i.e. the host name or
        GUID that this device publishes in the network's directory/discovery
        system.

    .. cpp:member:: OcaNetworkLinkType LinkType

        This property has id ``3.0``.

        Network link type - e.g. wired Ethernet, USB, ... See the
        OcaNetworkType enum for details. This is a read-only property whose
        value is fixed to the class that is inherited from OcaNetwork to
        implement each specific type of network.

    .. cpp:member:: OcaNetworkMediaProtocol MediaProtocol

        This property has id ``3.0``.

        Type of media transport protocol used by the network, or NONE if this
        network is not used for media transport.

    .. cpp:member:: OcaList<OcaONo> SignalChannelsSink

        This property has id ``3.0``.

        List of object numbers of _sink_ **OcaNetworkSignalChannel** objects
        collected by this network.

    .. cpp:member:: OcaList<OcaONo> SignalChannelsSource

        This property has id ``3.0``.

        List of object numbers of _source_ **OcaNetworkSignalChannel** objects
        collected by this network.

    .. cpp:member:: OcaNetworkStatistics Statistics

        This property has id ``3.0``.

        Error statistics for this network

    .. cpp:member:: OcaNetworkStatus Status

        This property has id ``3.0``.

        Operational status of the network.

    .. cpp:member:: OcaList<OcaONo> StreamConnectorsSink

        This property has id ``3.0``.

        List of object numbers of _sink_ **OcaStreamConnector** objects
        collected by this network.

    .. cpp:member:: OcaList<OcaONo> StreamConnectorsSource

        This property has id ``3.0``.

        List of object numbers of _source_ **OcaStreamConnector** objects
        collected by this network.

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceID> SystemInterfaces

        This property has id ``3.0``.

        Collection of identifiers of system interface(s) used by the network.
        A "system interface" is the system service through which network
        traffic passes into and out of the device -- e.g. a socket. The
        identifier format is system and network dependent; for OCA purposes,
        it is maintained as a variable-length blob which the protocol does not
        inspect.

    .. cpp:function:: OcaStatus GetLinkType(OcaNetworkLinkType &Type)

        This method has id ``3.1``.

        Gets the network's link type (wired Ethernet, USB, etc.). Return
        status indicates whether the operation was successful.

        :param OcaNetworkLinkType Type: Output parameter.

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaNetworkNodeID &Name)

        This method has id ``3.2``.

        Gets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaNetworkNodeID Name: Output parameter.

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaNetworkNodeID Name)

        This method has id ``3.3``.

        Sets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaNetworkNodeID Name: Input parameter.

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        This method has id ``3.4``.

        Gets the network's ControlProtocol property. Return status indicates
        whether the operation was successful.

        :param OcaNetworkControlProtocol Protocol: Output parameter.

    .. cpp:function:: OcaStatus GetMediaProtocol(OcaNetworkMediaProtocol &Protocol)

        This method has id ``3.5``.

        Gets the network's MediaProtocol property. Return status indicates
        whether the operation was successful.

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

    .. cpp:function:: OcaStatus GetStreamConnectorsSource(OcaList<OcaONo> &StreamConnectors)

        This method has id ``3.11``.

        Gets the list of object numbers of Source **OcaStreamConnector**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when **OcaStreamConnector**
        objects' **Owner** properties are updated, or when
        **OcaStreamConnector** objects are deleted. For reconfigurable
        devices, such changes may be initiated by controllers during device
        operation.

        :param OcaList<OcaONo> StreamConnectors: Output parameter.

    .. cpp:function:: OcaStatus SetStreamConnectorsSource(OcaList<OcaONo> StreamConnectors)

        This method has id ``3.12``.

        Sets the list of object numbers of Source **OcaStreamConnector**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when **OcaStreamConnector**
        objects' **Owner** properties are updated, or when
        **OcaStreamConnector** objects are deleted. For reconfigurable
        devices, such changes may be initiated by controllers during device
        operation.

        :param OcaList<OcaONo> StreamConnectors: Input parameter.

    .. cpp:function:: OcaStatus GetStreamConnectorsSink(OcaList<OcaONo> &StreamConnectors)

        This method has id ``3.13``.

        Gets the list of object numbers of Sink **OcaStreamConnector** objects
        owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when **OcaStreamConnector**
        objects' **Owner** properties are updated, or when
        **OcaStreamConnector** objects are deleted. For reconfigurable
        devices, such changes may be initiated by controllers during device
        operation.

        :param OcaList<OcaONo> StreamConnectors: Output parameter.

    .. cpp:function:: OcaStatus SetStreamConnectorsSink(OcaList<OcaONo> StreamConnectors)

        This method has id ``3.14``.

        Sets the list of object numbers of Sink **OcaStreamConnector** objects
        owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when **OcaStreamConnector**
        objects' **Owner** properties are updated, or when
        **OcaStreamConnector** objects are deleted. For reconfigurable
        devices, such changes may be initiated by controllers during device
        operation.

        :param OcaList<OcaONo> StreamConnectors: Input parameter.

    .. cpp:function:: OcaStatus GetSignalChannelsSource(OcaList<OcaONo> &SignalChannels)

        This method has id ``3.15``.

        Gets the list of object numbers of Source **OcaNetworkSignalChannel**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when
        **OcaNetworkSignalChannel** objects' **Owner** properties are updated,
        or when **OcaNetworkSignalChannel** objects are deleted. For
        reconfigurable devices, such changes may be initiated by controllers
        during device operation.

        :param OcaList<OcaONo> SignalChannels: Output parameter.

    .. cpp:function:: OcaStatus SetSignalChannelsSource(OcaList<OcaONo> SignalChannels)

        This method has id ``3.16``.

        Sets the list of object numbers of Source **OcaNetworkSignalChannel**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when
        **OcaNetworkSignalChannel** objects' **Owner** properties are updated,
        or when **OcaNetworkSignalChannel** objects are deleted. For
        reconfigurable devices, such changes may be initiated by controllers
        during device operation.

        :param OcaList<OcaONo> SignalChannels: Input parameter.

    .. cpp:function:: OcaStatus GetSignalChannelsSink(OcaList<OcaONo> &SignalChannels)

        This method has id ``3.17``.

        Gets the list of object numbers of Sink **OcaNetworkSignalChannel**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when
        **OcaNetworkSignalChannel** objects' **Owner** properties are updated,
        or when **OcaNetworkSignalChannel** objects are deleted. For
        reconfigurable devices, such changes may be initiated by controllers
        during device operation.

        :param OcaList<OcaONo> SignalChannels: Output parameter.

    .. cpp:function:: OcaStatus SetSignalChannelsSink(OcaList<OcaONo> SignalChannels)

        This method has id ``3.18``.

        Sets the list of object numbers of Sink **OcaNetworkSignalChannel**
        objects owned by this network. Return status indicates success of the
        operation. If the value of the network's MediaProtocol property is
        NONE, this method will return the status value InvalidRequest. Members
        are added to and deleted from this list when
        **OcaNetworkSignalChannel** objects' **Owner** properties are updated,
        or when **OcaNetworkSignalChannel** objects are deleted. For
        reconfigurable devices, such changes may be initiated by controllers
        during device operation.

        :param OcaList<OcaONo> SignalChannels: Input parameter.

    .. cpp:function:: OcaStatus Startup()

        This method has id ``3.19``.

        Start up this network.


    .. cpp:function:: OcaStatus Shutdown()

        This method has id ``3.20``.

        Shut down this network.


