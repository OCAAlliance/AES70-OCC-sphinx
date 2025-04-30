.. _ocaactuator:

1.1.1  OcaActuator
==================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>`

.. cpp:class:: OcaActuator: OcaWorker

    Abstract base class for all actuators (i.e. classes) that affect the routing
    and/or content of the audio signal, or provide ancillary control functions
    such as power).

    **Properties**:


    .. _ocaactuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaactuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    Properties inherited from :ref:`ocaworker`:

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


    **Methods**:


    Methods inherited from :ref:`ocaworker`:

    - :ref:`OcaWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaWorker::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaWorker::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaWorker::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaWorker::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaWorker::GetPath <ocaworker_getpath>`

    - :ref:`OcaWorker::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaWorker::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaWorker::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaWorker::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaWorker::SetPortName <ocaworker_setportname>`

