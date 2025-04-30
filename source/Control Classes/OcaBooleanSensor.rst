.. _ocabooleansensor:

1.1.2.1.1  OcaBooleanSensor
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaBasicSensor <ocabasicsensor>` : :ref:`OcaBooleanSensor <ocabooleansensor>`

.. cpp:class:: OcaBooleanSensor: OcaBasicSensor

    Boolean sensor

    **Properties**:


    .. _ocabooleansensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.1.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocabooleansensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocabooleansensor_reading:

    .. cpp:member:: OcaBoolean Reading

        Boolean reading.

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


    .. _ocabooleansensor_getreading:

    .. cpp:function:: OcaStatus GetReading(OcaBoolean &Reading)

        Gets the value of the **Reading** property.

        This method has id ``5.1``.

        - :cpp:expr:`Reading`: Output parameter.


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

