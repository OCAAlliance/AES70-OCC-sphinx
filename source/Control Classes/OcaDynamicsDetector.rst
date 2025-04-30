.. _ocadynamicsdetector:

1.1.1.15  OcaDynamicsDetector
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaDynamicsDetector <ocadynamicsdetector>`

.. cpp:class:: OcaDynamicsDetector: OcaActuator

    Dynamics element : side-chain detector.

    **Properties**:


    .. _ocadynamicsdetector_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.15"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadynamicsdetector_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocadynamicsdetector_law:

    .. cpp:member:: OcaLevelDetectionLaw Law

        Level detection law: RMS, Peak, possibly others

        This property has id ``4.1``.

    .. _ocadynamicsdetector_attacktime:

    .. cpp:member:: OcaTimeInterval AttackTime

        Detector attack time in seconds.

        This property has id ``4.2``.

    .. _ocadynamicsdetector_releasetime:

    .. cpp:member:: OcaTimeInterval ReleaseTime

        Detector release time in seconds.

        This property has id ``4.3``.

    .. _ocadynamicsdetector_holdtime:

    .. cpp:member:: OcaTimeInterval HoldTime

        Detector hold time in seconds.

        This property has id ``4.4``.

    Properties inherited from :ref:`ocaactuator`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocadynamicsdetector_getlaw:

    .. cpp:function:: OcaStatus GetLaw(OcaLevelDetectionLaw &Law)

        Gets the value of the Law property. Return status indicates whether the
        value was successfully retrieved.

        This method has id ``4.1``.

        - :cpp:expr:`Law`: Output parameter.


    .. _ocadynamicsdetector_setlaw:

    .. cpp:function:: OcaStatus SetLaw(OcaLevelDetectionLaw Law)

        Sets the value of the Law property. Return status indicates whether the
        value was successfully set.

        This method has id ``4.2``.

        - :cpp:expr:`Law`: Input parameter.


    .. _ocadynamicsdetector_getattacktime:

    .. cpp:function:: OcaStatus GetAttackTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the AttackTime property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.3``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamicsdetector_setattacktime:

    .. cpp:function:: OcaStatus SetAttackTime(OcaTimeInterval Time)

        Sets the value of the AttackTime property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.4``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamicsdetector_getreleasetime:

    .. cpp:function:: OcaStatus GetReleaseTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the ReleaseTime property. The return value indicates
        if the value was successfully retrieved.

        This method has id ``4.5``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamicsdetector_setreleasetime:

    .. cpp:function:: OcaStatus SetReleaseTime(OcaTimeInterval Time)

        Sets the value of the ReleaseTime property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.6``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamicsdetector_getholdtime:

    .. cpp:function:: OcaStatus GetHoldTime(OcaTimeInterval &Time, OcaTimeInterval &minTime, OcaTimeInterval &maxTime)

        Gets the value of the HoldTime property. The return value indicates if
        the value was successfully retrieved.

        This method has id ``4.7``.

        - :cpp:expr:`Time`: Output parameter.


        - :cpp:expr:`minTime`: Output parameter.


        - :cpp:expr:`maxTime`: Output parameter.


    .. _ocadynamicsdetector_setholdtime:

    .. cpp:function:: OcaStatus SetHoldTime(OcaTimeInterval Time)

        Sets the value of the HoldTime property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.8``.

        - :cpp:expr:`Time`: Input parameter.


    .. _ocadynamicsdetector_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaLevelDetectionLaw Law, OcaTimeInterval AttackTime, OcaTimeInterval ReleaseTime, OcaTimeInterval HoldTime)

        Sets some or all detector parameters. The return value indicates if the
        parameters were successfully set. The action of this method is atomic -
        if any of the value changes fails, none of the changes are made.

        This method has id ``4.9``.

        - :cpp:expr:`Mask`: Input parameter.


        - :cpp:expr:`Law`: Input parameter.


        - :cpp:expr:`AttackTime`: Input parameter.


        - :cpp:expr:`ReleaseTime`: Input parameter.


        - :cpp:expr:`HoldTime`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

