.. _ocapowersensor:

1.1.2.11  OcaPowerSensor
========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaPowerSensor <ocapowersensor>`

.. cpp:class:: OcaPowerSensor: OcaSensor

    Power sensor. Reading shall be a watts value and a power factor value.

    **Properties**:


    .. _ocapowersensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.11"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocapowersensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocapowersensor_power:

    .. cpp:member:: OcaFloat32 Power

        Power in watts.

        This property has id ``4.1``.

    .. _ocapowersensor_powerfactor:

    .. cpp:member:: OcaFloat32 PowerFactor

        Power factor. Value shall range from 1 to zero, with 1 applying to a
        purely resistive circuit.

        This property has id ``4.2``.

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


    .. _ocapowersensor_getreading:

    .. cpp:function:: OcaStatus GetReading(OcaFloat32 &Power, OcaFloat32 &PowerFactor, OcaFloat32 &minPower, OcaFloat32 &maxPower)

        Gets the value and limits of the **Power** property, and the value of
        the **PowerFactor** propert**y**.

        This method has id ``4.1``.

        - :cpp:expr:`Power`: Output parameter.


        - :cpp:expr:`PowerFactor`: Output parameter.


        - :cpp:expr:`minPower`: Output parameter.


        - :cpp:expr:`maxPower`: Output parameter.


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

