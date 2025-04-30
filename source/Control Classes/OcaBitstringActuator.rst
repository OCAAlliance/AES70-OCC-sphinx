.. _ocabitstringactuator:

1.1.1.1.13  OcaBitstringActuator
================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaBasicActuator <ocabasicactuator>` : :ref:`OcaBitstringActuator <ocabitstringactuator>`

.. cpp:class:: OcaBitstringActuator: OcaBasicActuator

    Bitstring actuator. Maximum bitstring length is 65,536 bits.

    **Properties**:


    .. _ocabitstringactuator_setting:

    .. cpp:member:: OcaBitstring Setting

        The bitstring data. New name for v3 of this class.

        This property has id ``5.1``.

    .. _ocabitstringactuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.1.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocabitstringactuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

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


    .. _ocabitstringactuator_getnrbits:

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &nrBits)

        Gets the number of bits in the string.

        This method has id ``5.1``.

        - :cpp:expr:`nrBits`: Output parameter.


    .. _ocabitstringactuator_getbit:

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaBoolean &Value)

        Gets the bit value of the given bit.

        This method has id ``5.2``.

        - :cpp:expr:`bitNr`: Input parameter.


        - :cpp:expr:`Value`: Output parameter.


    .. _ocabitstringactuator_setbit:

    .. cpp:function:: OcaStatus SetBit(OcaUint16 bitNr, OcaBoolean Value)

        Sets the bit value of the given bit.

        This method has id ``5.3``.

        - :cpp:expr:`bitNr`: Input parameter.


        - :cpp:expr:`Value`: Input parameter.


    .. _ocabitstringactuator_getsetting:

    .. cpp:function:: OcaStatus GetSetting(OcaBitstring &Setting)

        Gets the entire bitstring.

        This method has id ``5.4``.

        - :cpp:expr:`Setting`: Output parameter.


    .. _ocabitstringactuator_setsetting:

    .. cpp:function:: OcaStatus SetSetting(OcaBitstring Setting)

        Sets the entire bitstring.

        This method has id ``5.5``.

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

