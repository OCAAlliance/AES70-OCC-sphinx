.. _ocafilterarbitrarycurve:

1.1.1.13  OcaFilterArbitraryCurve
=================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaFilterArbitraryCurve <ocafilterarbitrarycurve>`

.. cpp:class:: OcaFilterArbitraryCurve: OcaActuator

    Arbitrary-curve filter, with transfer function specified as amplitude and
    phase versus frequency.

    **Properties**:


    .. _ocafilterarbitrarycurve_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocafilterarbitrarycurve_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocafilterarbitrarycurve_samplerate:

    .. cpp:member:: OcaFrequency SampleRate

        Sampling rate inside the filter. Note: This rate is not necessarily the
        same as the Device input or output sampling rate.

        This property has id ``4.2``.

    .. _ocafilterarbitrarycurve_tfmaxlength:

    .. cpp:member:: OcaUint16 TFMaxLength

        Maximum number of points that the transfer function may specify

        This property has id ``4.4``.

    .. _ocafilterarbitrarycurve_tfminlength:

    .. cpp:member:: OcaUint16 TFMinLength

        Minimum number of points that the transfer function must specify

        This property has id ``4.3``.

    .. _ocafilterarbitrarycurve_transferfunction:

    .. cpp:member:: OcaTransferFunction TransferFunction

        Transfer function of the filter.

        This property has id ``4.1``.

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


    .. _ocafilterarbitrarycurve_gettransferfunction:

    .. cpp:function:: OcaStatus GetTransferFunction(OcaTransferFunction &TransferFunction)

        Gets the complex transfer function.

        This method has id ``4.1``.

        - :cpp:expr:`TransferFunction`: Output parameter.


    .. _ocafilterarbitrarycurve_settransferfunction:

    .. cpp:function:: OcaStatus SetTransferFunction(OcaTransferFunction TransferFunction)

        Sets the complex transfer function.

        This method has id ``4.2``.

        - :cpp:expr:`TransferFunction`: Input parameter.


    .. _ocafilterarbitrarycurve_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the value and limits of the filter sampling rate.

        This method has id ``4.3``.

        - :cpp:expr:`Rate`: Output parameter.


        - :cpp:expr:`minRate`: Output parameter.


        - :cpp:expr:`maxRate`: Output parameter.


    .. _ocafilterarbitrarycurve_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the filter sampling rate.

        This method has id ``4.4``.

        - :cpp:expr:`Rate`: Input parameter.


    .. _ocafilterarbitrarycurve_gettfminlength:

    .. cpp:function:: OcaStatus GetTFMinLength(OcaUint16 &Min)

        Gets the value and limits of the TFMinLength property.

        This method has id ``4.5``.

        - :cpp:expr:`Min`: Output parameter.


    .. _ocafilterarbitrarycurve_gettfmaxlength:

    .. cpp:function:: OcaStatus GetTFMaxLength(OcaUint16 &Max)

        Gets the value and limits of the TFMaxLength property.

        This method has id ``4.6``.

        - :cpp:expr:`Max`: Output parameter.


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

