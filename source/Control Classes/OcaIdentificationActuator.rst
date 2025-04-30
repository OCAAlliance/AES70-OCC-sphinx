.. _ocaidentificationactuator:

1.1.1.21  OcaIdentificationActuator
===================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaIdentificationActuator <ocaidentificationactuator>`

.. cpp:class:: OcaIdentificationActuator: OcaActuator

    Function that shall turn on some kind of human-detectable indicator for
    purposes of device identification during network setup. Physical form of
    indicator is not specified by AES70, so it could be anything, e.g.

     - LED

     - Foghorn

     - Smoke emitter

     - Little waving robot hand wearing white glove

     - Jack-in-the-box popout

     - et cetera



    **Properties**:


    .. _ocaidentificationactuator_active:

    .. cpp:member:: OcaBoolean Active

        True if and only if indicator is active.

        This property has id ``4.1``.

    .. _ocaidentificationactuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.21"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaidentificationactuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

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


    .. _ocaidentificationactuator_getactive:

    .. cpp:function:: OcaStatus GetActive(OcaBoolean &active)

        Gets the value of the **Active** property.

        This method has id ``4.1``.

        - :cpp:expr:`active`: Output parameter.


    .. _ocaidentificationactuator_setactive:

    .. cpp:function:: OcaStatus SetActive(OcaBoolean active)

        Sets the value of the **Active** property.

        This method has id ``4.2``.

        - :cpp:expr:`active`: Input parameter.


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

