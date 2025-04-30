.. _ocabitstringsensor:

1.1.2.1.13  OcaBitstringSensor
==============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaBasicSensor <ocabasicsensor>` : :ref:`OcaBitstringSensor <ocabitstringsensor>`

.. cpp:class:: OcaBitstringSensor: OcaBasicSensor

    Bit string sensor.

    **Properties**:


    .. _ocabitstringsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.1.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocabitstringsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocabitstringsensor_bitstring:

    .. cpp:member:: OcaBitstring BitString

        The bitstring.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocabasicsensor`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaSensor::ClassID <ocasensor_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaSensor::ClassVersion <ocasensor_classversion>`

    - :cpp:texpr:`OcaSensorReadingState` :ref:`OcaSensor::ReadingState <ocasensor_readingstate>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaBasicSensor::ClassID <ocabasicsensor_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaBasicSensor::ClassVersion <ocabasicsensor_classversion>`


    **Methods**:


    .. _ocabitstringsensor_getnrbits:

    .. cpp:function:: OcaStatus GetNrBits(OcaUint16 &NrBits)

        Gets the number of bits of the bitmask data. Returned status indicates
        success or failure of the retrieval.

        This method has id ``5.1``.

        - :cpp:expr:`NrBits`: Output parameter.


    .. _ocabitstringsensor_getbit:

    .. cpp:function:: OcaStatus GetBit(OcaUint16 bitNr, OcaUint8 &bit)

        Gets the value of the given bit. Return status indicates success or
        failure of the retrieval.

        This method has id ``5.2``.

        - :cpp:expr:`bitNr`: Input parameter.


        - :cpp:expr:`bit`: Output parameter.


    .. _ocabitstringsensor_getbitstring:

    .. cpp:function:: OcaStatus GetBitString(OcaBitstring &BitString)

        Gets the entire bitstring. Return status indicates success or failure of
        the retrieval.

        This method has id ``5.3``.

        - :cpp:expr:`BitString`: Output parameter.


    Methods inherited from :ref:`ocabasicsensor`:

    - :ref:`OcaBasicSensor::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaBasicSensor::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaBasicSensor::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaBasicSensor::Unlock <ocaroot_unlock>`

    - :ref:`OcaBasicSensor::GetRole <ocaroot_getrole>`

    - :ref:`OcaBasicSensor::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaBasicSensor::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaBasicSensor::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaBasicSensor::AddPort <ocaworker_addport>`

    - :ref:`OcaBasicSensor::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaBasicSensor::GetPorts <ocaworker_getports>`

    - :ref:`OcaBasicSensor::GetPortName <ocaworker_getportname>`

    - :ref:`OcaBasicSensor::SetPortName <ocaworker_setportname>`

    - :ref:`OcaBasicSensor::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaBasicSensor::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaBasicSensor::GetOwner <ocaworker_getowner>`

    - :ref:`OcaBasicSensor::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaBasicSensor::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaBasicSensor::GetPath <ocaworker_getpath>`

    - :ref:`OcaBasicSensor::GetReadingState <ocasensor_getreadingstate>`

