.. _ocapowermanager:

1.3.5  OcaPowerManager
======================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaPowerManager: OcaManager

    Optional manager that manages power settings and state.
    
    - May be instantiated once in any device.
    
    
    - If instantiated, object number must be 5.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaPowerState State

        This property has id ``3.1``.

        Current power state of device. Readonly.

    .. cpp:member:: OcaList<OcaONo> PowerSupplies

        This property has id ``3.2``.

        List of object numbers of available power supplies.

    .. cpp:member:: OcaList<OcaONo> ActivePowerSupplies

        This property has id ``3.3``.

        Object number(s) of power suppl(ies) currently in use.

    .. cpp:member:: OcaBoolean AutoState

        This property has id ``3.4``.

        True if current state was invoked automatically, not by a controller
        action.

    .. cpp:member:: OcaPowerState TargetState

        This property has id ``3.5``.

        Power state to which the device is transitioning. If no transition is
        in progress, has value None. Readonly.

    .. cpp:function:: OcaStatus GetState(OcaPowerState &State)

        This method has id ``3.1``.

        Retrieve the value of property **03p01 State** , the current power
        state of the device. Return value indicates whether the value was
        successfully retrieved.

        :param OcaPowerState State: Output parameter.

    .. cpp:function:: OcaStatus SetState(OcaPowerState State)

        This method has id ``3.2``.

        Change the device power state. The return value indicates whether the
        requested change has been successfully made.

        :param OcaPowerState State: Input parameter.

    .. cpp:function:: OcaStatus GetPowerSupplies(OcaList<OcaONo> &psuList)

        This method has id ``3.3``.

        Retrieves list of object number(s) of all power supply(ies). Return
        value indicates whether the data was successfully retrieved.

        :param OcaList<OcaONo> psuList: Output parameter.

    .. cpp:function:: OcaStatus GetActivePowerSupplies(OcaList<OcaONo> &psuList)

        This method has id ``3.4``.

        Retrieves list of object number(s) of active power supply(ies). Return
        value indicates whether the data was successfully retrieved.

        :param OcaList<OcaONo> psuList: Output parameter.

    .. cpp:function:: OcaStatus ExchangePowerSupply(OcaONo oldPsu, OcaONo newPsu, OcaBoolean powerOffOld)

        This method has id ``3.5``.

        Deactivate one power supply and activate another. An option switch
        indicates whether the previously active power supply is to be turned
        off. If it is not turned off, it will be placed in the **Unavailable**
        state. The return value indicates whether the requested exchange has
        been successfully made.

        :param OcaONo oldPsu: Input parameter.
        :param OcaONo newPsu: Input parameter.
        :param OcaBoolean powerOffOld: Input parameter.

    .. cpp:function:: OcaStatus GetAutoState(OcaBoolean &state)

        This method has id ``3.6``.

        Gets the value of the **AutoState** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaBoolean state: Output parameter.

