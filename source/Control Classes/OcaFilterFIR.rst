.. _ocafilterfir:

1.1.1.12  OcaFilterFIR
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaFilterFIR <ocafilterfir>`

.. cpp:class:: OcaFilterFIR: OcaActuator

    Finite impulse response (FIR) filter.

    **Properties**:


    .. _ocafilterfir_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.12"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocafilterfir_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocafilterfir_coefficients:

    .. cpp:member:: OcaList<OcaFloat32> Coefficients

        Array of FIR Coefficients. Number of entries shall be equal to the value
        of the **Order** property plus 1.

        This property has id ``4.2``.

    .. _ocafilterfir_length:

    .. cpp:member:: OcaUint32 Length

        Length of the filter, in samples. Readonly.

        This property has id ``4.1``.

    .. _ocafilterfir_samplerate:

    .. cpp:member:: OcaFrequency SampleRate

        Sampling rate inside the filter. Note: This rate is not necessarily the
        same as the Device input or output sampling rate.

        This property has id ``4.3``.

    Properties inherited from :ref:`ocaactuator`:

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


    **Methods**:


    .. _ocafilterfir_getlength:

    .. cpp:function:: OcaStatus GetLength(OcaUint32 &Length, OcaUint32 &minLength, OcaUint32 &maxLength)

        Gets the length and length limits of the FIR filter.

        This method has id ``4.1``.

        - :cpp:expr:`Length`: Output parameter.


        - :cpp:expr:`minLength`: Output parameter.


        - :cpp:expr:`maxLength`: Output parameter.


    .. _ocafilterfir_getcoefficients:

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &Coefficients)

        Gets the coefficients of the FIR filter.

        This method has id ``4.2``.

        - :cpp:expr:`Coefficients`: Output parameter.


    .. _ocafilterfir_setcoefficients:

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> Coefficients)

        Sets the coefficients of the FIR filter.

        This method has id ``4.3``.

        - :cpp:expr:`Coefficients`: Input parameter.


    .. _ocafilterfir_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the value and limits of the **SampleRate** property.

        This method has id ``4.4``.

        - :cpp:expr:`Rate`: Output parameter.


        - :cpp:expr:`minRate`: Output parameter.


        - :cpp:expr:`maxRate`: Output parameter.


    .. _ocafilterfir_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the sampling rate of the FIR filter.

        This method has id ``4.5``.

        - :cpp:expr:`Rate`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaActuator::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

    - :ref:`OcaActuator::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaActuator::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaActuator::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

