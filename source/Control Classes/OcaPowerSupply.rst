.. _ocapowersupply:

1.2.7  OcaPowerSupply
=====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaPowerSupply <ocapowersupply>`

.. cpp:class:: OcaPowerSupply: OcaAgent

    A power supply.

    **Properties**:


    .. _ocapowersupply_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.7"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocapowersupply_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

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

    .. cpp:member:: const OcaPowerSupplyLocation Location

        Physical location of power supply - internal or external.

        This property has id ``3.7``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocapowersupply_gettype:

    .. cpp:function:: OcaStatus GetType(OcaPowerSupplyType &type)

        Gets the type of the power supply. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.1``.

        - :cpp:expr:`type`: Output parameter.


    .. _ocapowersupply_getmodelinfo:

    .. cpp:function:: OcaStatus GetModelInfo(OcaString &info)

        Gets the power supply's model information text. Return value indicates
        whether the data was successfully retrieved.

        This method has id ``3.2``.

        - :cpp:expr:`info`: Output parameter.


    .. _ocapowersupply_getstate:

    .. cpp:function:: OcaStatus GetState(OcaPowerSupplyState &state)

        Gets the state of the power supply. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`state`: Output parameter.


    .. _ocapowersupply_setstate:

    .. cpp:function:: OcaStatus SetState(OcaPowerSupplyState state)

        Changes the power supply's state. Return value indicates whether the
        state was successfully changed.

        This method has id ``3.4``.

        - :cpp:expr:`state`: Input parameter.


    .. _ocapowersupply_getcharging:

    .. cpp:function:: OcaStatus GetCharging(OcaBoolean &charging)

        Gets the value of property **Charging**. Return value indicates whether
        the value was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`charging`: Output parameter.


    .. _ocapowersupply_getloadfractionavailable:

    .. cpp:function:: OcaStatus GetLoadFractionAvailable(OcaFloat32 &fraction)

        Gets the available load fraction. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.6``.

        - :cpp:expr:`fraction`: Output parameter.


    .. _ocapowersupply_getstoragefractionavailable:

    .. cpp:function:: OcaStatus GetStorageFractionAvailable(OcaFloat32 &fraction)

        Gets the available storage fraction. Return value indicates whether the
        data was successfully retrieved.

        This method has id ``3.7``.

        - :cpp:expr:`fraction`: Output parameter.


    .. _ocapowersupply_getlocation:

    .. cpp:function:: OcaStatus GetLocation(OcaPowerSupplyLocation &Location)

        Gets the power supply physical location. Return value indicates whether
        the data was successfully retrieved.

        This method has id ``3.8``.

        - :cpp:expr:`Location`: Output parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

