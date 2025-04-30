.. _ocacontrolnetwork:

1.4.1  OcaControlNetwork
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaApplicationNetwork <ocaapplicationnetwork>` : :ref:`OcaControlNetwork <ocacontrolnetwork>`

.. cpp:class:: OcaControlNetwork: OcaApplicationNetwork


    **Properties**:


    .. _ocacontrolnetwork_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.4.1"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocacontrolnetwork_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocacontrolnetwork_protocol:

    .. cpp:member:: OcaNetworkControlProtocol Protocol

        Type of control protocol used by the network (OCAnn). Read-only
        property.

        This property has id ``3.1``.

    Properties inherited from :ref:`ocaapplicationnetwork`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaApplicationNetwork::ClassID <ocaapplicationnetwork_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaApplicationNetwork::ClassVersion <ocaapplicationnetwork_classversion>`

    - :cpp:texpr:`OcaUint16` :ref:`OcaApplicationNetwork::ErrorCode <ocaapplicationnetwork_errorcode>`

    - :cpp:texpr:`OcaString` :ref:`OcaApplicationNetwork::Label <ocaapplicationnetwork_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaApplicationNetwork::Owner <ocaapplicationnetwork_owner>`

    - :cpp:texpr:`OcaApplicationNetworkServiceID` :ref:`OcaApplicationNetwork::ServiceID <ocaapplicationnetwork_serviceid>`

    - :cpp:texpr:`OcaApplicationNetworkState` :ref:`OcaApplicationNetwork::State <ocaapplicationnetwork_state>`

    - :cpp:texpr:`OcaList<OcaNetworkSystemInterfaceDescriptor>` :ref:`OcaApplicationNetwork::SystemInterfaces <ocaapplicationnetwork_systeminterfaces>`


    **Methods**:


    .. _ocacontrolnetwork_getcontrolprotocol:

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        Gets the network's Protocol property. Return status indicates whether
        the operation was successful.

        This method has id ``3.1``.

        - :cpp:expr:`Protocol`: Output parameter.


    Methods inherited from :ref:`ocaapplicationnetwork`:

    - :ref:`OcaApplicationNetwork::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaApplicationNetwork::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaApplicationNetwork::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaApplicationNetwork::GetRole <ocaroot_getrole>`

    - :ref:`OcaApplicationNetwork::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaApplicationNetwork::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaApplicationNetwork::Unlock <ocaroot_unlock>`

    - :ref:`OcaApplicationNetwork::Control <ocaapplicationnetwork_control>`

    - :ref:`OcaApplicationNetwork::GetErrorCode <ocaapplicationnetwork_geterrorcode>`

    - :ref:`OcaApplicationNetwork::GetLabel <ocaapplicationnetwork_getlabel>`

    - :ref:`OcaApplicationNetwork::GetOwner <ocaapplicationnetwork_getowner>`

    - :ref:`OcaApplicationNetwork::GetPath <ocaapplicationnetwork_getpath>`

    - :ref:`OcaApplicationNetwork::GetServiceID <ocaapplicationnetwork_getserviceid>`

    - :ref:`OcaApplicationNetwork::GetState <ocaapplicationnetwork_getstate>`

    - :ref:`OcaApplicationNetwork::GetSystemInterfaces <ocaapplicationnetwork_getsysteminterfaces>`

    - :ref:`OcaApplicationNetwork::SetLabel <ocaapplicationnetwork_setlabel>`

    - :ref:`OcaApplicationNetwork::SetServiceID <ocaapplicationnetwork_setserviceid>`

    - :ref:`OcaApplicationNetwork::SetSystemInterfaces <ocaapplicationnetwork_setsysteminterfaces>`

