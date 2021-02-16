.. _ocadynamicsdetector:

1.1.1.15  OcaDynamicsDetector
=============================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaDynamicsDetector: OcaActuator

    Dynamics element : side-chain detector.

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

    .. cpp:member:: OcaLevelDetectionLaw Law

        This property has id ``4.0``.

        Level detection law: RMS, Peak, possibly others

    .. cpp:member:: OcaTimeInterval AttackTime

        This property has id ``4.0``.

        Detector attack time in seconds.

    .. cpp:member:: OcaTimeInterval ReleaseTime

        This property has id ``4.0``.

        Detector release time in seconds.

    .. cpp:member:: OcaTimeInterval HoldTime

        This property has id ``4.0``.

        Detector hold time in seconds.

    .. cpp:function:: OcaStatus GetLaw(OcaLevelDetectionLaw &Law)

        This method has id ``4.1``.

        Gets the value of the Law property. Return status indicates whether
        the value was successfully retrieved.

        :param OcaLevelDetectionLaw Law: Output parameter.

    .. cpp:function:: OcaStatus SetLaw(OcaLevelDetectionLaw Law)

        This method has id ``4.2``.

        Sets the value of the Law property. Return status indicates whether
        the value was successfully set.

        :param OcaLevelDetectionLaw Law: Input parameter.

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.3``.

        Gets the value of the AttackTime property. The return value indicates
        if the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        This method has id ``4.4``.

        Sets the value of the AttackTime property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.5``.

        Gets the value of the ReleaseTime property. The return value indicates
        if the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        This method has id ``4.6``.

        Sets the value of the ReleaseTime property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        This method has id ``4.7``.

        Gets the value of the HoldTime property. The return value indicates if
        the value was successfully retrieved.

        :param OcaTimeInterval Time: Output parameter.
        :param OcaTimeInterval minTime: Output parameter.
        :param OcaTimeInterval maxTime: Output parameter.

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        This method has id ``4.8``.

        Sets the value of the HoldTime property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval Time: Input parameter.

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaLevelDetectionLaw Law, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime)

        This method has id ``4.9``.

        Sets some or all detector parameters. The return value indicates if
        the parameters were successfully set. The action of this method is
        atomic - if any of the value changes fails, none of the changes are
        made.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaLevelDetectionLaw Law: Input parameter.
        :param OcaTimeInterval AttackTime: Input parameter.
        :param OcaTimeInterval ReleaseTime: Input parameter.
        :param OcaTimeInterval HoldTime: Input parameter.

