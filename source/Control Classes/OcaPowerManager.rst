.. _ocapowermanager:

1.3.5  OcaPowerManager
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaPowerManager <ocapowermanager>`

.. cpp:class:: OcaPowerManager: OcaManager

    Optional manager that manages power settings and state.

     - May be instantiated at most once in any device.

     - If instantiated, object number must be 5.



    **Properties**:


    .. _ocapowermanager_activepowersupplies:

    .. cpp:member:: OcaList<OcaONo> ActivePowerSupplies

        Object number(s) of power suppl(ies) currently in use.

        This property has id ``3.3``.

    .. _ocapowermanager_autostate:

    .. cpp:member:: OcaBoolean AutoState

        True if current state was invoked automatically, not by a controller
        action. Readonly.

        This property has id ``3.4``.

    .. _ocapowermanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.5"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocapowermanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocapowermanager_powersupplies:

    .. cpp:member:: OcaList<OcaONo> PowerSupplies

        List of object numbers of available power supplies.

        This property has id ``3.2``.

    .. _ocapowermanager_state:

    .. cpp:member:: OcaPowerState State

        Current power state of device. Readonly.

        This property has id ``3.1``.

    .. _ocapowermanager_targetstate:

    .. cpp:member:: OcaPowerState TargetState

        Power state to which the device is transitioning. If no transition is in
        progress, has value None. Set by calls to **SetTargetState()**.

        This property has id ``3.5``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocapowermanager_getstate:

    .. cpp:function:: OcaStatus GetState(OcaPowerState &State)

        Retrieve the value of property **State**, the current power state of the
        device.

        This method has id ``3.1``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocapowermanager_settargetstate:

    .. cpp:function:: OcaStatus SetTargetState(OcaPowerState State)

        Change the target power state. Erroneously named **SetState** prior to
        v3 of this class.

        This method has id ``3.2``.

        - :cpp:expr:`State`: Input parameter.


    .. _ocapowermanager_getpowersupplies:

    .. cpp:function:: OcaStatus GetPowerSupplies(OcaList<OcaONo> &psuList)

        Retrieves list of object number(s) of all power supply(ies).

        This method has id ``3.3``.

        - :cpp:expr:`psuList`: Output parameter.


    .. _ocapowermanager_getactivepowersupplies:

    .. cpp:function:: OcaStatus GetActivePowerSupplies(OcaList<OcaONo> &psuList)

        Retrieves list of object number(s) of active power supply(ies).

        This method has id ``3.4``.

        - :cpp:expr:`psuList`: Output parameter.


    .. _ocapowermanager_exchangepowersupply:

    .. cpp:function:: OcaStatus ExchangePowerSupply(OcaONo oldPsu, OcaONo newPsu, OcaBoolean powerOffOld)

        Deactivate one power supply and activate another. An option switch
        indicates whether the previously active power supply is to be turned
        off. If it is not turned off, it will be placed in the **Unavailable**
        state.

        This method has id ``3.5``.

        - :cpp:expr:`oldPsu`: Input parameter.


        - :cpp:expr:`newPsu`: Input parameter.


        - :cpp:expr:`powerOffOld`: Input parameter.


    .. _ocapowermanager_getautostate:

    .. cpp:function:: OcaStatus GetAutoState(OcaBoolean &state)

        Gets the value of the **AutoState** property.

        This method has id ``3.6``.

        - :cpp:expr:`state`: Output parameter.


    .. _ocapowermanager_gettargetstate:

    .. cpp:function:: OcaStatus GetTargetState(OcaPowerState &State)

        Retrieve the value of property** TargetState**, the power state of the
        device to which the device is transitioning.

        This method has id ``3.7``.

        - :cpp:expr:`State`: Output parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

