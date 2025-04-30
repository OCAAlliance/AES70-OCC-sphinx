.. _ocastringsensor:

1.1.2.1.12  OcaStringSensor
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaBasicSensor <ocabasicsensor>` : :ref:`OcaStringSensor <ocastringsensor>`

.. cpp:class:: OcaStringSensor: OcaBasicSensor

    UTF-8 string sensor.

    **Properties**:


    .. _ocastringsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.1.12"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocastringsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocastringsensor_maxlen:

    .. cpp:member:: OcaUint16 MaxLen

        Maximum length of the returned string. May be readonly in some
        implementations.

        This property has id ``5.2``.

    .. _ocastringsensor_reading:

    .. cpp:member:: OcaString Reading

        The string. New name as of v3 of this class.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocabasicsensor`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaSensor::ClassID <ocasensor_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaSensor::ClassVersion <ocasensor_classversion>`

    - :cpp:texpr:`OcaSensorReadingState` :ref:`OcaSensor::ReadingState <ocasensor_readingstate>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaBasicSensor::ClassID <ocabasicsensor_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaBasicSensor::ClassVersion <ocabasicsensor_classversion>`


    **Methods**:


    .. _ocastringsensor_getreading:

    .. cpp:function:: OcaStatus GetReading(OcaString &Reading)

        Gets the entire string.

        This method has id ``5.1``.

        - :cpp:expr:`Reading`: Output parameter.


    .. _ocastringsensor_getmaxlen:

    .. cpp:function:: OcaStatus GetMaxLen(OcaUint16 &maxLen)

        Gets the maximum number of bytes that may be returned.

        This method has id ``5.2``.

        - :cpp:expr:`maxLen`: Output parameter.


    .. _ocastringsensor_setmaxlen:

    .. cpp:function:: OcaStatus SetMaxLen(OcaUint16 maxLen)

        Sets the maximum number of bytes that the object may return.

        This method has id ``5.3``.

        - :cpp:expr:`maxLen`: Input parameter.


    Methods inherited from :ref:`ocabasicsensor`:

    - :ref:`OcaBasicSensor::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaBasicSensor::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaBasicSensor::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaBasicSensor::GetRole <ocaroot_getrole>`

    - :ref:`OcaBasicSensor::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaBasicSensor::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaBasicSensor::Unlock <ocaroot_unlock>`

    - :ref:`OcaBasicSensor::AddPort <ocaworker_addport>`

    - :ref:`OcaBasicSensor::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaBasicSensor::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaBasicSensor::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaBasicSensor::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaBasicSensor::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaBasicSensor::GetOwner <ocaworker_getowner>`

    - :ref:`OcaBasicSensor::GetPath <ocaworker_getpath>`

    - :ref:`OcaBasicSensor::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaBasicSensor::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaBasicSensor::GetPortName <ocaworker_getportname>`

    - :ref:`OcaBasicSensor::GetPorts <ocaworker_getports>`

    - :ref:`OcaBasicSensor::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaBasicSensor::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaBasicSensor::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaBasicSensor::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaBasicSensor::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaBasicSensor::SetPortName <ocaworker_setportname>`

    - :ref:`OcaBasicSensor::GetReadingState <ocasensor_getreadingstate>`

