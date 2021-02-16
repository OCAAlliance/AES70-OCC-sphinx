.. _ocaapplicationnetwork:

1.4  OcaApplicationNetwork
==========================

Extends :ref:`OcaRoot <ocaroot>`.

.. cpp:class:: OcaApplicationNetwork: OcaRoot

    Abstract base class from which the application network classes
    inherit.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``2.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``2.2``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaString Label

        This property has id ``2.1``.

        Specific label of the network. Can be used to provide human readable
        information about the network. The label can be get and set over any
        network.

    .. cpp:member:: OcaONo Owner

        This property has id ``2.2``.

        Object number of block that contains this network.

    .. cpp:member:: OcaApplicationNetworkServiceID ServiceID

        This property has id ``2.3``.

        Name or GUID that this device publishes in the network's
        directory/discovery system to designate the services offered via this
        application network object. This may or may not be the same as the
        device's host name, if any. For data network types that have host
        names (e.g. IP networks), the authoritative copy of the host name is
        in the system interface ID.

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceDescriptor> SystemInterfaces

        This property has id ``2.4``.

        Collection of identifiers of system interface descriptor(s) used by
        the network. A "system interface" is the system service through which
        network traffic passes into and out of the device -- e.g. a socket.
        The descriptor format is system and network dependent; for OCA
        purposes, it is maintained as a variable-length blob which the
        protocol does not inspect.

    .. cpp:member:: OcaApplicationNetworkState State

        This property has id ``2.5``.

        Operational state of the network.

    .. cpp:member:: OcaUint16 ErrorCode

        This property has id ``2.6``.

        Most recent error code. 0=no error.

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        This method has id ``2.1``.

        Gets the network's user-specified label. Return status indicates
        whether the operation was successful.

        :param OcaString Label: Output parameter.

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        This method has id ``2.2``.

        Sets the network's user-specified label. Return status indicates
        whether the operation was successful.

        :param OcaString Label: Input parameter.

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        This method has id ``2.3``.

        Gets the ONo of this network's containing block. Return status
        indicates whether the operation was successful.

        :param OcaONo Owner: Output parameter.

    .. cpp:function:: OcaStatus GetServiceID(OcaApplicationNetworkServiceID &Name)

        This method has id ``2.4``.

        Gets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaApplicationNetworkServiceID Name: Output parameter.

    .. cpp:function:: OcaStatus SetServiceID(OcaApplicationNetworkServiceID Name)

        This method has id ``2.5``.

        Sets the network's IDAdvertised. Return status indicates whether the
        operation was successful.

        :param OcaApplicationNetworkServiceID Name: Input parameter.

    .. cpp:function:: OcaStatus GetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceDescriptor> &SystemInterfaces)

        This method has id ``2.6``.

        Retrieves the list of this network's system interface descriptor.
        Return status indicates whether the list was successfully retrieved.

        :param OcaList<OcaNetworkSystemInterfaceDescriptor> SystemInterfaces: Output parameter.

    .. cpp:function:: OcaStatus SetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceDescriptor> Descriptors)

        This method has id ``2.7``.

        Sets the network's System Interface Descriptor(s). Return status
        indicates whether the operation was successful. Optional method;
        System Interface Descriptor may be set at construction time.

        :param OcaList<OcaNetworkSystemInterfaceDescriptor> Descriptors: Input parameter.

    .. cpp:function:: OcaStatus GetState(OcaApplicationNetworkState &State)

        This method has id ``2.8``.

        Retrieves the network's state. Return status indicates whether the
        status was successfully retrieved.

        :param OcaApplicationNetworkState State: Output parameter.

    .. cpp:function:: OcaStatus GetErrorCode(OcaUint16 &ErrorCode)

        This method has id ``2.9``.

        Retrieves the most recent error code. Return status indicates whether
        the operation was successful. Note that a second parameter 'Reset' is
        removed in v02 of this class.

        :param OcaUint16 ErrorCode: Output parameter.

    .. cpp:function:: OcaStatus Control(OcaApplicationNetworkCommand Command)

        This method has id ``2.10``.

        Control the application network. Return value indicates success of
        command execution.

        :param OcaApplicationNetworkCommand Command: Input parameter.

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        This method has id ``2.11``.

        Returns path from given object down to root. The return value
        indicates whether the operation succeeded.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.

