.. _ocamute:

1.1.1.2  OcaMute
================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaMute: OcaActuator

    Signal mute.

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

    .. cpp:member:: OcaMuteState State

        This property has id ``4.1``.

        Current state of the mute.

    .. cpp:function:: OcaStatus GetState(OcaMuteState &state)

        This method has id ``4.1``.

        Gets the current mute state. The return value indicates whether the
        state was successfully retrieved.

        :param OcaMuteState state: Output parameter.

    .. cpp:function:: OcaStatus SetState(OcaMuteState state)

        This method has id ``4.2``.

        Sets the mute state (i.e. value of the State property). The return
        value indicates whether the state was successfully set.

        :param OcaMuteState state: Input parameter.

