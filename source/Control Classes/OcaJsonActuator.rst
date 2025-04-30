.. _ocajsonactuator:

1.1.1.1.14  OcaJsonActuator
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaBasicActuator <ocabasicactuator>` : :ref:`OcaJsonActuator <ocajsonactuator>`

.. cpp:class:: OcaJsonActuator: OcaBasicActuator

    JSON value actuator.

    **Properties**:


    .. _ocajsonactuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.1.14"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocajsonactuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocajsonactuator_maxlen:

    .. cpp:member:: const OcaUint16 MaxLen

        Maximum allowed byte length of the **Value** property. Read-only.

        This property has id ``5.2``.

    .. _ocajsonactuator_value:

    .. cpp:member:: OcaJsonValue Value

        The JSON value.

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


    .. _ocajsonactuator_getvalue:

    .. cpp:function:: OcaStatus GetValue(OcaJsonValue &Value)

        Gets the value of the **Value** property.

        This method has id ``5.1``.

        - :cpp:expr:`Value`: Output parameter.


    .. _ocajsonactuator_setvalue:

    .. cpp:function:: OcaStatus SetValue(OcaJsonValue Setting)

        Sets the value of the **Value** property.

        This method has id ``5.2``.

        - :cpp:expr:`Setting`: Input parameter.


    .. _ocajsonactuator_getmaxlen:

    .. cpp:function:: OcaStatus GetMaxLen(OcaUint16 &Len)

        Output parameter that shall hold the maximum allowable length of the
        Setting property if the method succeeds.

        This method has id ``5.3``.

        - :cpp:expr:`Len`: Output parameter.


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

