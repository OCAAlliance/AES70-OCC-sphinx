.. _ocapanbalance:

1.1.1.6  OcaPanBalance
======================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaPanBalance: OcaActuator

    Pan or Balance control.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaFloat32 Position

        This property has id ``4.1``.

        Pan position. Range = -1.0 to +1.0. -1.0 is 100% left, +1.0 is 100%
        right.

    .. cpp:member:: OcaDB MidpointGain

        This property has id ``4.2``.

        Midpoint gain. Normally, max=0dB, min=-6dB. May be readonly for
        pan/balance objects with fixed midpoint gains.

    .. cpp:function:: OcaStatus GetPosition(OcaFloat32 &Position, OcaFloat32 &minPosition, OcaFloat32 &maxPosition)

        This method has id ``4.1``.

        Gets the value and limits of the Position property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaFloat32 Position: Output parameter.
        :param OcaFloat32 minPosition: Output parameter.
        :param OcaFloat32 maxPosition: Output parameter.

    .. cpp:function:: OcaStatus SetPosition(OcaFloat32 Position)

        This method has id ``4.2``.

        Sets the value of the Position property. The return value indicates
        whether the property was successfully set.

        :param OcaFloat32 Position: Input parameter.

    .. cpp:function:: OcaStatus GetMidpointGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``4.3``.

        Gets the value and limits of the MidpointGain property. The return
        value indicates whether the data was successfully retrieved.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. cpp:function:: OcaStatus SetMidpointGain(OcaDB Gain)

        This method has id ``4.4``.

        Sets the value of the MidpointGain property. The return value
        indicates whether the property was successfully set.

        :param OcaDB Gain: Input parameter.

