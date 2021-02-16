.. _ocaaudiolevelsensor:

1.1.2.2.1  OcaAudioLevelSensor
==============================

Extends :ref:`OcaLevelSensor <ocalevelsensor>`.

.. cpp:class:: OcaAudioLevelSensor: OcaLevelSensor

    Child of **OcaLevelSensor** that returns an audio meter reading in dB
    relative to a known reference level, and whose value has been
    calculated by the selected averaging algorithm.

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

    .. cpp:member:: OcaLevelMeterLaw Law

        This property has id ``5.1``.

        Enum that defines metering algorithm, including averaging
        characteristics and, in some cases, reference level. Readonly in some
        objects.

    .. cpp:function:: OcaStatus GetLaw(OcaLevelMeterLaw &law)

        This method has id ``5.1``.

        Gets the value of the Law property. The return value indicates whether
        the property was successfully retrieved.

        :param OcaLevelMeterLaw law: Output parameter.

    .. cpp:function:: OcaStatus SetLaw(OcaLevelMeterLaw law)

        This method has id ``5.2``.

        Sets the value of the Law property. The return value indicates whether
        the property was successfully set. Only implemented for objects whose
        Law property is read/write.

        :param OcaLevelMeterLaw law: Input parameter.

