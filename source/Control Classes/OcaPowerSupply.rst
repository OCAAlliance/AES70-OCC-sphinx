.. _ocapowersupply:

1.2.7  OcaPowerSupply
=====================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaPowerSupply <ocapowersupply>` 

.. cpp:class:: OcaPowerSupply: OcaAgent

    A power supply.

    **Properties**:

    .. _ocapowersupply_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocapowersupply_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocapowersupply_type:

    .. cpp:member:: OcaPowerSupplyType Type

        Type of power supply.

        This property has id ``3.1``.

    .. _ocapowersupply_modelinfo:

    .. cpp:member:: OcaString ModelInfo

        Model information for power supply. Text; content is
        implementation-dependent.

        This property has id ``3.2``.

    .. _ocapowersupply_state:

    .. cpp:member:: OcaPowerSupplyState State

        State of power supply: off, unavailable, available, active.

        This property has id ``3.3``.

    .. _ocapowersupply_charging:

    .. cpp:member:: OcaBoolean Charging

        True iff charging. For rechargable supplies (obviously).

        This property has id ``3.4``.

    .. _ocapowersupply_loadfractionavailable:

    .. cpp:member:: OcaFloat32 LoadFractionAvailable

        Fraction of power supply's load capacity that is currently not being
        used. Readonly. Normal value range 0...1. A negative value indicates
        this data is not available.

        This property has id ``3.5``.

    .. _ocapowersupply_storagefractionavailable:

    .. cpp:member:: OcaFloat32 StorageFractionAvailable

        Fraction of power supply's energy storage that remains available. For
        battery supplies. Readonly. Normal value range 0...1. A negative value
        indicates this data is not available.

        This property has id ``3.6``.

    .. _ocapowersupply_location:

    .. cpp:member:: OcaPowerSupplyLocation Location

        Physical location of power supply - internal or external.

        This property has id ``3.7``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocapowersupply_gettype:

    .. cpp:function:: OcaStatus GetType(OcaPowerSupplyType &type)

        Gets the type of the power supply. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.1``.

        :param OcaPowerSupplyType type: Output parameter.

    .. _ocapowersupply_getmodelinfo:

    .. cpp:function:: OcaStatus GetModelInfo(OcaString &info)

        Gets the power supply's model information text. Return value indicates
        whether the data was successfully retrieved.

        This method has id ``3.2``.

        :param OcaString info: Output parameter.

    .. _ocapowersupply_getstate:

    .. cpp:function:: OcaStatus GetState(OcaPowerSupplyState &state)

        Gets the state of the power supply. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.3``.

        :param OcaPowerSupplyState state: Output parameter.

    .. _ocapowersupply_setstate:

    .. cpp:function:: OcaStatus SetState(OcaPowerSupplyState state)

        Changes the power supply's state. Return value indicates whether the
        state was successfully changed.

        This method has id ``3.4``.

        :param OcaPowerSupplyState state: Input parameter.

    .. _ocapowersupply_getcharging:

    .. cpp:function:: OcaStatus GetCharging(OcaBoolean &charging)

        Gets the value of property **Charging** . Return value indicates
        whether the value was successfully retrieved.

        This method has id ``3.5``.

        :param OcaBoolean charging: Output parameter.

    .. _ocapowersupply_getloadfractionavailable:

    .. cpp:function:: OcaStatus GetLoadFractionAvailable(OcaFloat32 &fraction)

        Gets the available load fraction. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.6``.

        :param OcaFloat32 fraction: Output parameter.

    .. _ocapowersupply_getstoragefractionavailable:

    .. cpp:function:: OcaStatus GetStorageFractionAvailable(OcaFloat32 &fraction)

        Gets the available storage fraction. Return value indicates whether
        the data was successfully retrieved.

        This method has id ``3.7``.

        :param OcaFloat32 fraction: Output parameter.

    .. _ocapowersupply_getlocation:

    .. cpp:function:: OcaStatus GetLocation(OcaPowerSupplyLocation &Location)

        Gets the power supply physical location. Return value indicates
        whether the data was successfully retrieved.

        This method has id ``3.8``.

        :param OcaPowerSupplyLocation Location: Output parameter.


    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
