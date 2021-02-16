.. _ocadelay:

1.1.1.7  OcaDelay
=================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaDelay: OcaActuator

    Signal delay - basic version.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaTimeInterval DelayTime

        This property has id ``4.0``.

        Delay in seconds.

    .. cpp:function:: OcaStatus GetDelayTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.1``.

        Gets the value of the DelayTime property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetDelayTime(OcaTimeInterval delayTime)

        This method has id ``4.2``.

        Sets the value of the DelayTime property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval delayTime: Input parameter.

