.. _ocabitstringactuator:

1.1.1.1.13  OcaBitstringActuator
================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaBasicActuator <ocabasicactuator>` : :ref:`OcaBitstringActuator <ocabitstringactuator>`

.. cpp:class:: OcaBitstringActuator: OcaBasicActuator

    Bitstring actuator. Maximum bitstring length is 65,536 bits.

    **Properties**:


    .. _ocabitstringactuator_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.1.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocabitstringactuator_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocabitstringactuator_bitstring:

    .. cpp:member:: OcaBitstring Bitstring

        The bitstring data.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocabasicactuator`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaBasicActuator::ClassID <ocabasicactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaBasicActuator::ClassVersion <ocabasicactuator_classversion>`


    **Methods**:


    .. _ocabitstringactuator_getnrbits:

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &nrBits)

        Gets the number of bits in the string. The return value indicates
        whether the property was successfully gathered.

        This method has id ``5.1``.

        - :cpp:expr:`nrBits`: Output parameter.


    .. _ocabitstringactuator_getbit:

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaBoolean &Value)

        Gets the bit value of the given bit. The return value indicates whether
        the property was successfully gathered.

        This method has id ``5.2``.

        - :cpp:expr:`bitNr`: Input parameter.


        - :cpp:expr:`Value`: Output parameter.


    .. _ocabitstringactuator_setbit:

    .. cpp:function:: OcaStatus SetBit(OcaUint16 bitNr, OcaBoolean Value)

        Sets the bit value of the given bit. The return value indicates whether
        the property was successfully set.

        This method has id ``5.3``.

        - :cpp:expr:`bitNr`: Input parameter.


        - :cpp:expr:`Value`: Input parameter.


    .. _ocabitstringactuator_getbitstring:

    .. cpp:function:: OcaStatus GetBitstring(OcaBitstring &BitString)

        Gets the entire bitstring.The return value indicates whether the
        property was successfully gathered.

        This method has id ``5.4``.

        - :cpp:expr:`BitString`: Output parameter.


    .. _ocabitstringactuator_setbitstring:

    .. cpp:function:: OcaStatus SetBitstring(OcaBitstring BitString)

        Sets the entire bitstring. The return value indicates whether the
        property was successfully set.

        This method has id ``5.5``.

        - :cpp:expr:`BitString`: Input parameter.


    Methods inherited from :ref:`ocabasicactuator`:

    - :ref:`OcaBasicActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaBasicActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaBasicActuator::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaBasicActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaBasicActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaBasicActuator::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaBasicActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaBasicActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaBasicActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaBasicActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaBasicActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaBasicActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaBasicActuator::SetPortName <ocaworker_setportname>`

    - :ref:`OcaBasicActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaBasicActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaBasicActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaBasicActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaBasicActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaBasicActuator::GetPath <ocaworker_getpath>`

