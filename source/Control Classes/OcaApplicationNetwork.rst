.. _ocaapplicationnetwork:

1.4  OcaApplicationNetwork
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaApplicationNetwork <ocaapplicationnetwork>` 

.. cpp:class:: OcaApplicationNetwork: OcaRoot

    Abstract base class from which the application network classes inherit.

    **Properties**:

    .. _ocaapplicationnetwork_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.4"

        This property is an override of the  **OcaRoot** property.

        This property has id ``2.1``.

    .. _ocaapplicationnetwork_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the  **OcaRoot** property.

        This property has id ``2.2``.

    .. _ocaapplicationnetwork_label:

    .. cpp:member:: static OcaString Label

        Specific label of the network. Can be used to provide human readable information about the network. The label can be get and set over any network.

        This property has id ``2.1``.

    .. _ocaapplicationnetwork_owner:

    .. cpp:member:: static OcaONo Owner

        Object number of block that contains this network.

        This property has id ``2.2``.

    .. _ocaapplicationnetwork_serviceid:

    .. cpp:member:: OcaApplicationNetworkServiceID ServiceID

        Name or GUID that this device publishes in the network's directory/discovery system to designate the services offered via this application network object. This may or may not be the same as the device's host name, if any. For data network types that have host names (e.g. IP networks), the authoritative copy of the host name is in the system interface ID.

        This property has id ``2.3``.

    .. _ocaapplicationnetwork_systeminterfaces:

    .. cpp:member:: OcaList<OcaNetworkSystemInterfaceDescriptor> SystemInterfaces

        Collection of identifiers of system interface descriptor(s) used by the network. A "system interface" is the system service through which network traffic passes into and out of the device -- e.g. a socket. The descriptor format is system and network dependent; for OCA purposes, it is maintained as a variable-length blob which the protocol does not inspect.

        This property has id ``2.4``.

    .. _ocaapplicationnetwork_state:

    .. cpp:member:: OcaApplicationNetworkState State

        Operational state of the network.

        This property has id ``2.5``.

    .. _ocaapplicationnetwork_errorcode:

    .. cpp:member:: OcaUint16 ErrorCode

        Most recent error code. 0=no error.

        This property has id ``2.6``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocaapplicationnetwork_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the network's user-specified label. Return status indicates whether the operation was successful.

        This method has id ``2.1``.

        :param OcaString Label: Output parameter.

    .. _ocaapplicationnetwork_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the network's user-specified label. Return status indicates whether the operation was successful.

        This method has id ``2.2``.

        :param OcaString Label: Input parameter.

    .. _ocaapplicationnetwork_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        Gets the ONo of this network's containing block. Return status indicates whether the operation was successful.

        This method has id ``2.3``.

        :param OcaONo Owner: Output parameter.

    .. _ocaapplicationnetwork_getserviceid:

    .. cpp:function:: OcaStatus GetServiceID(OcaApplicationNetworkServiceID &Name)

        Gets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``2.4``.

        :param OcaApplicationNetworkServiceID Name: Output parameter.

    .. _ocaapplicationnetwork_setserviceid:

    .. cpp:function:: OcaStatus SetServiceID(OcaApplicationNetworkServiceID Name)

        Sets the network's IDAdvertised. Return status indicates whether the operation was successful.

        This method has id ``2.5``.

        :param OcaApplicationNetworkServiceID Name: Input parameter.

    .. _ocaapplicationnetwork_getsysteminterfaces:

    .. cpp:function:: OcaStatus GetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceDescriptor> &SystemInterfaces)

        Retrieves the list of this network's system interface descriptor. Return status indicates whether the list was successfully retrieved.

        This method has id ``2.6``.

        :param OcaList<OcaNetworkSystemInterfaceDescriptor> SystemInterfaces: Output parameter.

    .. _ocaapplicationnetwork_setsysteminterfaces:

    .. cpp:function:: OcaStatus SetSystemInterfaces(OcaList<OcaNetworkSystemInterfaceDescriptor> Descriptors)

        Sets the network's System Interface Descriptor(s). Return status indicates whether the operation was successful. Optional method; System Interface Descriptor may be set at construction time.

        This method has id ``2.7``.

        :param OcaList<OcaNetworkSystemInterfaceDescriptor> Descriptors: Input parameter.

    .. _ocaapplicationnetwork_getstate:

    .. cpp:function:: OcaStatus GetState(OcaApplicationNetworkState &State)

        Retrieves the network's state. Return status indicates whether the status was successfully retrieved.

        This method has id ``2.8``.

        :param OcaApplicationNetworkState State: Output parameter.

    .. _ocaapplicationnetwork_geterrorcode:

    .. cpp:function:: OcaStatus GetErrorCode(OcaUint16 &ErrorCode)

        Retrieves the most recent error code. Return status indicates whether the operation was successful. Note that a second parameter 'Reset' is removed in v02 of this class.

        This method has id ``2.9``.

        :param OcaUint16 ErrorCode: Output parameter.

    .. _ocaapplicationnetwork_control:

    .. cpp:function:: OcaStatus Control(OcaApplicationNetworkCommand Command)

        Control the application network. Return value indicates success of command execution.

        This method has id ``2.10``.

        :param OcaApplicationNetworkCommand Command: Input parameter.

    .. _ocaapplicationnetwork_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        Returns path from given object down to root. The return value indicates whether the operation succeeded.

        This method has id ``2.11``.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


