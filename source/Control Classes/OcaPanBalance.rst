.. _ocapanbalance:

1.1.1.6  OcaPanBalance
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaPanBalance <ocapanbalance>`

.. cpp:class:: OcaPanBalance: OcaActuator

    Pan or Balance control.

    **Properties**:


    .. _ocapanbalance_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.6"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocapanbalance_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocapanbalance_midpointgain:

    .. cpp:member:: OcaDB MidpointGain

        Midpoint gain. Normally, max=0dB, min=-6dB. May be readonly for
        pan/balance objects with fixed midpoint gains.

        This property has id ``4.2``.

    .. _ocapanbalance_position:

    .. cpp:member:: OcaFloat32 Position

        Pan position. Range = -1.0 to +1.0. -1.0 is 100% left, +1.0 is 100%
        right.

        This property has id ``4.1``.

    Properties inherited from :ref:`ocaactuator`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaMap<OcaPortID, OcaPortClockMapEntry>` :ref:`OcaWorker::PortClockMap <ocaworker_portclockmap>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocapanbalance_getposition:

    .. cpp:function:: OcaStatus GetPosition(OcaFloat32 &Position, OcaFloat32 &minPosition, OcaFloat32 &maxPosition)

        Gets the value and limits of the **Position** property.

        This method has id ``4.1``.

        - :cpp:expr:`Position`: Output parameter.


        - :cpp:expr:`minPosition`: Output parameter.


        - :cpp:expr:`maxPosition`: Output parameter.


    .. _ocapanbalance_setposition:

    .. cpp:function:: OcaStatus SetPosition(OcaFloat32 Position)

        Sets the value of the **Position** property.

        This method has id ``4.2``.

        - :cpp:expr:`Position`: Input parameter.


    .. _ocapanbalance_getmidpointgain:

    .. cpp:function:: OcaStatus GetMidpointGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the value and limits of the **MidpointGain** property.

        This method has id ``4.3``.

        - :cpp:expr:`Gain`: Output parameter.


        - :cpp:expr:`minGain`: Output parameter.


        - :cpp:expr:`maxGain`: Output parameter.


    .. _ocapanbalance_setmidpointgain:

    .. cpp:function:: OcaStatus SetMidpointGain(OcaDB Gain)

        Sets the value of the **MidpointGain** property.

        This method has id ``4.4``.

        - :cpp:expr:`Gain`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaActuator::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

    - :ref:`OcaActuator::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaActuator::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaActuator::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

