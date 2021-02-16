.. _ocapowersupply:

1.2.7  OcaPowerSupply
=====================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaPowerSupply: OcaAgent

    A power supply.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaPowerSupplyType Type

        This property has id ``3.0``.

        Type of power supply.

    .. cpp:member:: OcaString ModelInfo

        This property has id ``3.0``.

        Model information for power supply. Text; content is
        implementation-dependent.

    .. cpp:member:: OcaPowerSupplyState State

        This property has id ``3.0``.

        State of power supply: off, unavailable, available, active.

    .. cpp:member:: OcaBoolean Charging

        This property has id ``3.0``.

        True iff charging. For rechargable supplies (obviously).

    .. cpp:member:: OcaFloat32 LoadFractionAvailable

        This property has id ``3.0``.

        Fraction of power supply's load capacity that is currently not being
        used. Readonly. Normal value range 0...1. A negative value indicates
        this data is not available.

    .. cpp:member:: OcaFloat32 StorageFractionAvailable

        This property has id ``3.0``.

        Fraction of power supply's energy storage that remains available. For
        battery supplies. Readonly. Normal value range 0...1. A negative value
        indicates this data is not available.

    .. cpp:member:: OcaPowerSupplyLocation Location

        This property has id ``3.0``.

        Physical location of power supply - internal or external.

    .. cpp:function:: OcaStatus GetType(OcaPowerSupplyType &type)

        This method has id ``3.1``.

        Gets the type of the power supply. Return value indicates whether the
        data was successfully retrieved.

        :param OcaPowerSupplyType type: Output parameter.

    .. cpp:function:: OcaStatus GetModelInfo(OcaString &info)

        This method has id ``3.2``.

        Gets the power supply's model information text. Return value indicates
        whether the data was successfully retrieved.

        :param OcaString info: Output parameter.

    .. cpp:function:: OcaStatus GetState(OcaPowerSupplyState &state)

        This method has id ``3.3``.

        Gets the state of the power supply. Return value indicates whether the
        data was successfully retrieved.

        :param OcaPowerSupplyState state: Output parameter.

    .. cpp:function:: OcaStatus SetState(OcaPowerSupplyState state)

        This method has id ``3.4``.

        Changes the power supply's state. Return value indicates whether the
        state was successfully changed.

        :param OcaPowerSupplyState state: Input parameter.

    .. cpp:function:: OcaStatus GetCharging(OcaBoolean &charging)

        This method has id ``3.5``.

        Gets the value of property **Charging** . Return value indicates
        whether the value was successfully retrieved.

        :param OcaBoolean charging: Output parameter.

    .. cpp:function:: OcaStatus GetLoadFractionAvailable(OcaFloat32 &fraction)

        This method has id ``3.6``.

        Gets the available load fraction. Return value indicates whether the
        data was successfully retrieved.

        :param OcaFloat32 fraction: Output parameter.

    .. cpp:function:: OcaStatus GetStorageFractionAvailable(OcaFloat32 &fraction)

        This method has id ``3.7``.

        Gets the available storage fraction. Return value indicates whether
        the data was successfully retrieved.

        :param OcaFloat32 fraction: Output parameter.

    .. cpp:function:: OcaStatus GetLocation(OcaPowerSupplyLocation &Location)

        This method has id ``3.8``.

        Gets the power supply physical location. Return value indicates
        whether the data was successfully retrieved.

        :param OcaPowerSupplyLocation Location: Output parameter.

