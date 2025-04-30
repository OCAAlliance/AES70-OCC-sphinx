.. _ocaaudiolevelsensor:

1.1.2.2.1  OcaAudioLevelSensor
==============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaLevelSensor <ocalevelsensor>` : :ref:`OcaAudioLevelSensor <ocaaudiolevelsensor>`

.. cpp:class:: OcaAudioLevelSensor: OcaLevelSensor

    Child of **OcaLevelSensor** that returns an audio meter reading in dB
    relative to a known reference level, and whose value has been calculated by
    the selected averaging algorithm.

    **Properties**:


    .. _ocaaudiolevelsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.2.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaaudiolevelsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaaudiolevelsensor_law:

    .. cpp:member:: OcaLevelMeterLaw Law

        Enum that defines metering algorithm, including averaging
        characteristics and, in some cases, reference level. Readonly in some
        objects.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocalevelsensor`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaLevelSensor::ClassID <ocalevelsensor_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaLevelSensor::ClassVersion <ocalevelsensor_classversion>`

    - :cpp:texpr:`OcaDB` :ref:`OcaLevelSensor::Reading <ocalevelsensor_reading>`


    **Methods**:


    .. _ocaaudiolevelsensor_getlaw:

    .. cpp:function:: OcaStatus GetLaw(OcaLevelMeterLaw &law)

        Gets the value of the Law property. The return value indicates whether
        the property was successfully retrieved.

        This method has id ``5.1``.

        - :cpp:expr:`law`: Output parameter.


    .. _ocaaudiolevelsensor_setlaw:

    .. cpp:function:: OcaStatus SetLaw(OcaLevelMeterLaw law)

        Sets the value of the Law property. The return value indicates whether
        the property was successfully set. Only implemented for objects whose
        Law property is read/write.

        This method has id ``5.2``.

        - :cpp:expr:`law`: Input parameter.


    Methods inherited from :ref:`ocalevelsensor`:

    - :ref:`OcaLevelSensor::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaLevelSensor::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaLevelSensor::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaLevelSensor::Unlock <ocaroot_unlock>`

    - :ref:`OcaLevelSensor::GetRole <ocaroot_getrole>`

    - :ref:`OcaLevelSensor::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaLevelSensor::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaLevelSensor::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaLevelSensor::AddPort <ocaworker_addport>`

    - :ref:`OcaLevelSensor::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaLevelSensor::GetPorts <ocaworker_getports>`

    - :ref:`OcaLevelSensor::GetPortName <ocaworker_getportname>`

    - :ref:`OcaLevelSensor::SetPortName <ocaworker_setportname>`

    - :ref:`OcaLevelSensor::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaLevelSensor::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaLevelSensor::GetOwner <ocaworker_getowner>`

    - :ref:`OcaLevelSensor::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaLevelSensor::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaLevelSensor::GetPath <ocaworker_getpath>`

    - :ref:`OcaLevelSensor::GetReadingState <ocasensor_getreadingstate>`

    - :ref:`OcaLevelSensor::GetReading <ocalevelsensor_getreading>`

