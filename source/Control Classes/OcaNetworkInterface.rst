.. _ocanetworkinterface:

1.6  OcaNetworkInterface
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaNetworkInterface <ocanetworkinterface>`

.. cpp:class:: OcaNetworkInterface: OcaRoot

    Represents the device's connection to a data network.

    **Properties**:


    .. _ocanetworkinterface_activenetworksettings:

    .. cpp:member:: OcaAdaptationData ActiveNetworkSettings

        Network-type-specific settings currently in effect.

        This property has id ``2.8``.

    .. _ocanetworkinterface_adaptationidentifier:

    .. cpp:member:: OcaAdaptationIdentifier AdaptationIdentifier

        Null string in the base class. Value will be overridden in subclasses by
        the identifier of the Adaptation that defined the respective child
        class.

        This property has id ``2.7``.

    .. _ocanetworkinterface_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.6"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocanetworkinterface_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocanetworkinterface_enabled:

    .. cpp:member:: OcaBoolean Enabled

        True if and only if this network is available for input and/or output.

        This property has id ``2.3``.

    .. _ocanetworkinterface_errorcode:

    .. cpp:member:: OcaUint16 ErrorCode

        Most recent error code. 0=no error.

        This property has id ``2.12``.

    .. _ocanetworkinterface_groupid:

    .. cpp:member:: OcaUint16 GroupID

        Arbitrary ID of network group to which this network interface belongs.
        Useful for identifying redundant network sets. An ID value of zero means
        this network interface does not belong to any group.

        This property has id ``2.5``.

    .. _ocanetworkinterface_label:

    .. cpp:member:: OcaString Label

        User-defined label. No programmatic significance. Read/write.

        This property has id ``2.1``.

    .. _ocanetworkinterface_networksettingspending:

    .. cpp:member:: OcaBoolean NetworkSettingsPending

        Readonly; TRUE when a new **TargetNetworkSettings** value has been
        provided but not applied; set to TRUE by method
        **SetTargetNetworkSettings(...)**, set to FALSE when the target network
        settings are applied, either by the execution of a **Start** command or
        by some other means.

        This property has id ``2.10``.

    .. _ocanetworkinterface_owner:

    .. cpp:member:: const OcaONo Owner

        Object number of block that contains this object. Read-only.

        This property has id ``2.2``.

    .. _ocanetworkinterface_precedence:

    .. cpp:member:: OcaUint16 Precedence

        Used for redundant groups. 0 means undefined. 1 is highest priority, 2
        is next, and so on.

        This property has id ``2.6``.

    .. _ocanetworkinterface_status:

    .. cpp:member:: OcaNetworkInterfaceStatus Status

        Operational status of this network interface

        This property has id ``2.11``.

    .. _ocanetworkinterface_systemiointerfacename:

    .. cpp:member:: OcaString SystemIoInterfaceName

        Name of the network I/O interface provided to AES70 by the Device system
        environment.

        This property has id ``2.4``.

    .. _ocanetworkinterface_targetnetworksettings:

    .. cpp:member:: OcaAdaptationData TargetNetworkSettings

        Network-type-specific settings waiting to be applied. Shall be applied
        by a **Start** or **Restart** command or by a Device-initiated reset.
        The value of this property may or may not survive a Device reset,
        depending on implementation.

        This property has id ``2.9``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocanetworkinterface_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the value of the **Label** property.

        This method has id ``2.1``.

        - :cpp:expr:`Label`: Output parameter.


    .. _ocanetworkinterface_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the value of the **Label** property.

        This method has id ``2.2``.

        - :cpp:expr:`Label`: Input parameter.


    .. _ocanetworkinterface_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        Gets the value of the **Owner** property.

        This method has id ``2.3``.

        - :cpp:expr:`Owner`: Output parameter.


    .. _ocanetworkinterface_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaRolePath &RolePath, OcaONoPath &ONoPath)

        Returns Role Path and ONo Path from the Root Block to this object. The
        return value indicates whether the operation succeeded.

        This method has id ``2.4``.

        - :cpp:expr:`RolePath`: Output parameter.


        - :cpp:expr:`ONoPath`: Output parameter.


    .. _ocanetworkinterface_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &Enabled)

        Gets the value of the **Enabled** property.

        This method has id ``2.5``.

        - :cpp:expr:`Enabled`: Output parameter.


    .. _ocanetworkinterface_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean Enabled)

        Sets the value of the **Enabled** property.

        This method has id ``2.6``.

        - :cpp:expr:`Enabled`: Input parameter.


    .. _ocanetworkinterface_getsystemiointerfacename:

    .. cpp:function:: OcaStatus GetSystemIoInterfaceName(OcaString &Name)

        Gets the system I/O interface name.

        This method has id ``2.7``.

        - :cpp:expr:`Name`: Output parameter.


    .. _ocanetworkinterface_setsystemiointerfacename:

    .. cpp:function:: OcaStatus SetSystemIoInterfaceName(OcaString Identifier)

        Sets the system I/O interface name.

        This method has id ``2.8``.

        - :cpp:expr:`Identifier`: Input parameter.


    .. _ocanetworkinterface_getgroupid:

    .. cpp:function:: OcaStatus GetGroupID(OcaUint16 &Id)

        Gets the network group ID. Returns value of zero if this network does
        not belong to a group.

        This method has id ``2.9``.

        - :cpp:expr:`Id`: Output parameter.


    .. _ocanetworkinterface_setgroupid:

    .. cpp:function:: OcaStatus SetGroupID(OcaUint16 Id)

        Sets the network group ID. An ID value of zero means this network
        interface does not belong to a group.

        This method has id ``2.10``.

        - :cpp:expr:`Id`: Input parameter.


    .. _ocanetworkinterface_getprecedence:

    .. cpp:function:: OcaStatus GetPrecedence(OcaUint8 &Precedence)

        Gets the value of the **Precedence** property.

        This method has id ``2.11``.

        - :cpp:expr:`Precedence`: Output parameter.


    .. _ocanetworkinterface_setprecedence:

    .. cpp:function:: OcaStatus SetPrecedence(OcaUint8 Precedence)

        Sets the value of the **Precedence** property.

        This method has id ``2.12``.

        - :cpp:expr:`Precedence`: Input parameter.


    .. _ocanetworkinterface_getadaptationidentifier:

    .. cpp:function:: OcaStatus GetAdaptationIdentifier(OcaString &Identifier)

        Gets the identifier of the Adaptation this network object implements.

        This method has id ``2.13``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocanetworkinterface_getactivenetworksettings:

    .. cpp:function:: OcaStatus GetActiveNetworkSettings(OcaBlob &Settings)

        Gets the value of property **ActiveNetworkSettings.**

        This method has id ``2.14``.

        - :cpp:expr:`Settings`: Output parameter.


    .. _ocanetworkinterface_gettargetnetworksettings:

    .. cpp:function:: OcaStatus GetTargetNetworkSettings(OcaBlob &Settings)

        Gets the value of property **TargetNetworkSettings.**

        This method has id ``2.15``.

        - :cpp:expr:`Settings`: Output parameter.


    .. _ocanetworkinterface_settargetnetworksettings:

    .. cpp:function:: OcaStatus SetTargetNetworkSettings(OcaBlob Settings)

        Sets the value of property **TargetNetworkSettings.**

        This method has id ``2.16``.

        - :cpp:expr:`Settings`: Input parameter.


    .. _ocanetworkinterface_getnetworksettingspending:

    .. cpp:function:: OcaStatus GetNetworkSettingsPending(OcaBoolean &Pending)

        Gets the value of property **NetworkSettingsPending.**

        This method has id ``2.17``.

        - :cpp:expr:`Pending`: Output parameter.


    .. _ocanetworkinterface_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaNetworkInterfaceStatus &Status)

        Gets the network's operational status.

        This method has id ``2.18``.

        - :cpp:expr:`Status`: Output parameter.


    .. _ocanetworkinterface_geterrorcode:

    .. cpp:function:: OcaStatus GetErrorCode(OcaUint16 &ErrorCode)

        Gets the most recent error code.

        This method has id ``2.19``.

        - :cpp:expr:`ErrorCode`: Output parameter.


    .. _ocanetworkinterface_getcounterset:

    .. cpp:function:: OcaStatus GetCounterSet(OcaCounterSet &CounterSet)

        Get this object's CounterSet.

        This method has id ``2.20``.

        - :cpp:expr:`CounterSet`: Output parameter.


    .. _ocanetworkinterface_getcounter:

    .. cpp:function:: OcaStatus GetCounter(OcaID16 CounterID, OcaCounter &Counter)

        Gets the given counter from this object's CounterSet.

        This method has id ``2.21``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`Counter`: Output parameter.


    .. _ocanetworkinterface_attachcounternotifier:

    .. cpp:function:: OcaStatus AttachCounterNotifier(OcaID16 CounterID, OcaONo ONo)

        Adds a notifier **ONo** to the **Notifiers** property of the designated
        counter.

        This method has id ``2.22``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`ONo`: Input parameter.


    .. _ocanetworkinterface_detachcounternotifier:

    .. cpp:function:: OcaStatus DetachCounterNotifier(OcaID16 CounterID, OcaONo ONo)

        Removes given notifier ONo from the **Notifiers** property of the
        designated counter.

        This method has id ``2.23``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`ONo`: Input parameter.


    .. _ocanetworkinterface_resetcounters:

    .. cpp:function:: OcaStatus ResetCounters()

        Resets this object's counterset. Sets all counters to their specified
        default values.

        This method has id ``2.24``.

    .. _ocanetworkinterface_applycommand:

    .. cpp:function:: OcaStatus ApplyCommand(OcaNetworkInterfaceCommand Command)

        Controls the network interface.

        This method has id ``2.25``.

        - :cpp:expr:`Command`: Input parameter.


    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaRoot::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

