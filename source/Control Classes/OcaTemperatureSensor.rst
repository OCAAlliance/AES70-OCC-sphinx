.. _ocatemperaturesensor:

1.1.2.5  OcaTemperatureSensor
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaTemperatureSensor <ocatemperaturesensor>`

.. cpp:class:: OcaTemperatureSensor: OcaSensor

    Temperature sensor. Units of measure are Celsius.

    **Properties**:


    .. _ocatemperaturesensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.5"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocatemperaturesensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocatemperaturesensor_reading:

    .. cpp:member:: OcaTemperature Reading

        Temperature value (Celsius).

        This property has id ``4.1``.

    Properties inherited from :ref:`ocasensor`:

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


    **Methods**:


    .. _ocatemperaturesensor_getreading:

    .. cpp:function:: OcaStatus GetReading(OcaTemperature &Reading, OcaTemperature &minReading, OcaTemperature &maxReading)

        Gets the value and limits of the **Reading** property.

        This method has id ``4.1``.

        - :cpp:expr:`Reading`: Output parameter.


        - :cpp:expr:`minReading`: Output parameter.


        - :cpp:expr:`maxReading`: Output parameter.


    Methods inherited from :ref:`ocasensor`:

    - :ref:`OcaSensor::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaSensor::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaSensor::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaSensor::GetRole <ocaroot_getrole>`

    - :ref:`OcaSensor::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaSensor::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaSensor::Unlock <ocaroot_unlock>`

    - :ref:`OcaSensor::AddPort <ocaworker_addport>`

    - :ref:`OcaSensor::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaSensor::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaSensor::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaSensor::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaSensor::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaSensor::GetOwner <ocaworker_getowner>`

    - :ref:`OcaSensor::GetPath <ocaworker_getpath>`

    - :ref:`OcaSensor::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaSensor::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaSensor::GetPortName <ocaworker_getportname>`

    - :ref:`OcaSensor::GetPorts <ocaworker_getports>`

    - :ref:`OcaSensor::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaSensor::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaSensor::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaSensor::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaSensor::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaSensor::SetPortName <ocaworker_setportname>`

    - :ref:`OcaSensor::GetReadingState <ocasensor_getreadingstate>`

