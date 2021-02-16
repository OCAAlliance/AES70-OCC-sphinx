.. _ocapolarity:

1.1.1.3  OcaPolarity
====================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaPolarity: OcaActuator

    Signal inverter

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

    .. cpp:member:: OcaPolarityState State

        This property has id ``4.1``.

        Current state of the inverter - {noninverted, inverted].

    .. cpp:function:: OcaStatus GetState(OcaPolarityState &state)

        This method has id ``4.1``.

        Gets the current inverter state. The return value indicates whether
        the state was successfully retrieved.

        :param OcaPolarityState state: Output parameter.

    .. cpp:function:: OcaStatus SetState(OcaPolarityState state)

        This method has id ``4.2``.

        Sets the inversion state (i.e. value of the State property). The
        return value indicates whether the state was successfully set.

        :param OcaPolarityState state: Input parameter.

