.. _ocapowermanager:

1.3.5  OcaPowerManager
======================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaPowerManager <ocapowermanager>` 

.. cpp:class:: OcaPowerManager: OcaManager

    Optional manager that manages power settings and state.  
    
     - May be instantiated once in any device.
     
    
     - If instantiated, object number must be 5.
     

    **Properties**:

    .. _ocapowermanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocapowermanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocapowermanager_state:

    .. cpp:member:: OcaPowerState State

        Current power state of device. Readonly.

        This property has id ``3.1``.

    .. _ocapowermanager_powersupplies:

    .. cpp:member:: OcaList<OcaONo> PowerSupplies

        List of object numbers of available power supplies.

        This property has id ``3.2``.

    .. _ocapowermanager_activepowersupplies:

    .. cpp:member:: OcaList<OcaONo> ActivePowerSupplies

        Object number(s) of power suppl(ies) currently in use.

        This property has id ``3.3``.

    .. _ocapowermanager_autostate:

    .. cpp:member:: OcaBoolean AutoState

        True if current state was invoked automatically, not by a controller action.

        This property has id ``3.4``.

    .. _ocapowermanager_targetstate:

    .. cpp:member:: OcaPowerState TargetState

        Power state to which the device is transitioning. If no transition is in progress, has value None. Readonly.

        This property has id ``3.5``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocapowermanager_getstate:

    .. cpp:function:: OcaStatus GetState(OcaPowerState &State)

        Retrieve the value of property  **03p01 State** , the current power state of the device. Return value indicates whether the value was successfully retrieved.

        This method has id ``3.1``.

        :param OcaPowerState State: Output parameter.

    .. _ocapowermanager_setstate:

    .. cpp:function:: OcaStatus SetState(OcaPowerState State)

        Change the device power state. The return value indicates whether the requested change has been successfully made.

        This method has id ``3.2``.

        :param OcaPowerState State: Input parameter.

    .. _ocapowermanager_getpowersupplies:

    .. cpp:function:: OcaStatus GetPowerSupplies(OcaList<OcaONo> &psuList)

        Retrieves list of object number(s) of all power supply(ies). Return value indicates whether the data was successfully retrieved.

        This method has id ``3.3``.

        :param OcaList<OcaONo> psuList: Output parameter.

    .. _ocapowermanager_getactivepowersupplies:

    .. cpp:function:: OcaStatus GetActivePowerSupplies(OcaList<OcaONo> &psuList)

        Retrieves list of object number(s) of active power supply(ies). Return value indicates whether the data was successfully retrieved.

        This method has id ``3.4``.

        :param OcaList<OcaONo> psuList: Output parameter.

    .. _ocapowermanager_exchangepowersupply:

    .. cpp:function:: OcaStatus ExchangePowerSupply(OcaONo oldPsu, OcaONo newPsu, OcaBoolean powerOffOld)

        Deactivate one power supply and activate another. An option switch indicates whether the previously active power supply is to be turned off. If it is not turned off, it will be placed in the  **Unavailable**  state. The return value indicates whether the requested exchange has been successfully made.

        This method has id ``3.5``.

        :param OcaONo oldPsu: Input parameter.
        :param OcaONo newPsu: Input parameter.
        :param OcaBoolean powerOffOld: Input parameter.

    .. _ocapowermanager_getautostate:

    .. cpp:function:: OcaStatus GetAutoState(OcaBoolean &state)

        Gets the value of the  **AutoState**  property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.6``.

        :param OcaBoolean state: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


