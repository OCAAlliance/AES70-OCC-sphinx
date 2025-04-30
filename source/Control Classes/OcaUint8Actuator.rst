.. _ocauint8actuator:

1.1.1.1.6  OcaUint8Actuator
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaBasicActuator <ocabasicactuator>` : :ref:`OcaUint8Actuator <ocauint8actuator>`

.. cpp:class:: OcaUint8Actuator: OcaBasicActuator

    8-bit unsigned integer actuator

    **Properties**:


    .. _ocauint8actuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.1.6"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocauint8actuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocauint8actuator_setting:

    .. cpp:member:: OcaUint8 Setting

        Uint8 setting.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocabasicactuator`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaBasicActuator::ClassID <ocabasicactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaBasicActuator::ClassVersion <ocabasicactuator_classversion>`


    **Methods**:


    .. _ocauint8actuator_getsetting:

    .. cpp:function:: OcaStatus GetSetting(OcaUint8 &Setting, OcaUint8 &minSetting, OcaUint8 &maxSetting)

        Gets the value and limits of the **Setting** property.

        This method has id ``5.1``.

        - :cpp:expr:`Setting`: Output parameter.


        - :cpp:expr:`minSetting`: Output parameter.


        - :cpp:expr:`maxSetting`: Output parameter.


    .. _ocauint8actuator_setsetting:

    .. cpp:function:: OcaStatus SetSetting(OcaUint8 Setting)

        Sets the **Setting** property.

        This method has id ``5.2``.

        - :cpp:expr:`Setting`: Input parameter.


    Methods inherited from :ref:`ocabasicactuator`:

    - :ref:`OcaBasicActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaBasicActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaBasicActuator::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaBasicActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaBasicActuator::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaBasicActuator::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaBasicActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaBasicActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaBasicActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaBasicActuator::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaBasicActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaBasicActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaBasicActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaBasicActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaBasicActuator::GetPath <ocaworker_getpath>`

    - :ref:`OcaBasicActuator::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaBasicActuator::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaBasicActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaBasicActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaBasicActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaBasicActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaBasicActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaBasicActuator::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaBasicActuator::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaBasicActuator::SetPortName <ocaworker_setportname>`

