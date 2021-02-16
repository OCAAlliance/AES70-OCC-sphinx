.. _ocadelayextended:

1.1.1.7.1  OcaDelayExtended
===========================

Extends :ref:`OcaDelay <ocadelay>`.

.. cpp:class:: OcaDelayExtended: OcaDelay

    Signal delay - extended version. Allows setting delay value in various
    units. Note that the inherited property 04p01 DelayTime is also
    supported by this class and reflects actual achieved delay in seconds.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``5.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``5.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaDelayValue DelayValue

        This property has id ``5.1``.

        Delay value.

    .. cpp:function:: OcaStatus GetDelayValue(OcaDelayValue &Value, OcaDelayValue &minValue, OcaDelayValue &maxValue)

        This method has id ``5.1``.

        Gets the value of the DelayValue property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaDelayValue Value: Output parameter.
        :param OcaDelayValue minValue: Output parameter.
        :param OcaDelayValue maxValue: Output parameter.

    .. cpp:function:: OcaStatus SetDelayValue(OcaDelayValue Value)

        This method has id ``5.2``.

        Sets the value of the DelayValue property. The return value indicates
        whether the property was successfully set.

        :param OcaDelayValue Value: Input parameter.

    .. cpp:function:: OcaStatus GetDelayValueConverted(OcaDelayUnit UoM, OcaDelayValue &Value)

        This method has id ``5.3``.

        Return current delay setting, converted to given units. The return
        value indicates whether the method has succeeded.

        :param OcaDelayUnit UoM: Input parameter.
        :param OcaDelayValue Value: Output parameter.

