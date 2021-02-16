.. _ocagain:

1.1.1.5  OcaGain
================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaGain: OcaActuator

    Gain (or attenuation) element.

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

    .. cpp:member:: OcaDB Gain

        This property has id ``4.1``.

        Gain in dB.

    .. cpp:function:: OcaStatus GetGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``4.1``.

        Gets the value and limits of the Gain property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. cpp:function:: OcaStatus SetGain(OcaDB Gain)

        This method has id ``4.2``.

        Sets the value of the Gain property. The return value indicates
        whether the property was successfully set.

        :param OcaDB Gain: Input parameter.

