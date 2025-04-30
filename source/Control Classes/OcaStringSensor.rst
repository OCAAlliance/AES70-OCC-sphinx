.. _ocastringsensor:

1.1.2.1.12  OcaStringSensor
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaSensor <ocasensor>` : :ref:`OcaBasicSensor <ocabasicsensor>` : :ref:`OcaStringSensor <ocastringsensor>`

.. cpp:class:: OcaStringSensor: OcaBasicSensor

    Text string sensor.

    **Properties**:


    .. _ocastringsensor_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.2.1.12"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocastringsensor_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocastringsensor_string:

    .. cpp:member:: OcaString String

        The string.

        This property has id ``5.1``.

    .. _ocastringsensor_maxlen:

    .. cpp:member:: OcaUint16 MaxLen

        Maximum length of the returned string. May be readonly in some
        implementations.

        This property has id ``5.2``.

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


    .. _ocastringsensor_getstring:

    .. cpp:function:: OcaStatus GetString(OcaString &String)

        Gets the entire string. Return status indicates success or failure of
        the retrieval.

        This method has id ``5.1``.

        - :cpp:expr:`String`: Output parameter.


    .. _ocastringsensor_getmaxlen:

    .. cpp:function:: OcaStatus GetMaxLen(OcaUint16 &maxLen)

        Gets the maximum number of bytes that may be returned. Returned status
        indicates success or failure of the retrieval.

        This method has id ``5.2``.

        - :cpp:expr:`maxLen`: Output parameter.


    .. _ocastringsensor_setmaxlen:

    .. cpp:function:: OcaStatus SetMaxLen(OcaUint16 maxLen)

        Sets the maximum number of bytes that the object may return. Returned
        status indicates success or failure of the set.

        This method has id ``5.3``.

        - :cpp:expr:`maxLen`: Input parameter.


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

