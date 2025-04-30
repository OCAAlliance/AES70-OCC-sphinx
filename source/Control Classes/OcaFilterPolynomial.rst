.. _ocafilterpolynomial:

1.1.1.11  OcaFilterPolynomial
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaFilterPolynomial <ocafilterpolynomial>`

.. cpp:class:: OcaFilterPolynomial: OcaActuator

    Generic Z-domain rational polynomial filter section with transfer function
    expression of the form: A(0) + A(1)z + A(2)z^2 + A(3)z^3 + ... B(0) + B(1)z
    + B(2)z^2 + B(3)z^3 + ...

    **Properties**:


    .. _ocafilterpolynomial_a:

    .. cpp:member:: OcaList<OcaFloat32> A

        Numerator - "A"

        This property has id ``4.1``.

    .. _ocafilterpolynomial_b:

    .. cpp:member:: OcaList<OcaFloat32> B

        Denominator - "B"

        This property has id ``4.2``.

    .. _ocafilterpolynomial_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.11"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocafilterpolynomial_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocafilterpolynomial_maxorder:

    .. cpp:member:: const OcaUint8 MaxOrder

        Maximum order of A[] and B[], i.e. the maximum size of the A[] and B[]
        arrays. Readonly.

        This property has id ``4.4``.

    .. _ocafilterpolynomial_samplerate:

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


    .. _ocafilterpolynomial_getcoefficients:

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &A, OcaList<OcaFloat32> &B)

        Gets the polynomial coefficients.

        This method has id ``4.1``.

        - :cpp:expr:`A`: Output parameter.


        - :cpp:expr:`B`: Output parameter.


    .. _ocafilterpolynomial_setcoefficients:

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> A, OcaList<OcaFloat32> B)

        Sets the polynomial coefficients.

        This method has id ``4.2``.

        - :cpp:expr:`A`: Input parameter.


        - :cpp:expr:`B`: Input parameter.


    .. _ocafilterpolynomial_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the filter sampling rate value and limits.

        This method has id ``4.3``.

        - :cpp:expr:`Rate`: Output parameter.


        - :cpp:expr:`minRate`: Output parameter.


        - :cpp:expr:`maxRate`: Output parameter.


    .. _ocafilterpolynomial_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the filter sampling rate.

        This method has id ``4.4``.

        - :cpp:expr:`Rate`: Input parameter.


    .. _ocafilterpolynomial_getmaxorder:

    .. cpp:function:: OcaStatus GetMaxOrder(OcaUint8 &Order)

        Gets the maximum allowable order (= max number of array elements in
        numerator and for denominator arrays)

        This method has id ``4.5``.

        - :cpp:expr:`Order`: Output parameter.


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

