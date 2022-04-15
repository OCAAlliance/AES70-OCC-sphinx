.. _ocafilterpolynomial:

1.1.1.11  OcaFilterPolynomial
=============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaFilterPolynomial <ocafilterpolynomial>` 

.. cpp:class:: OcaFilterPolynomial: OcaActuator

    A generic Z-domain rational polynomial filter section:  _A(0) + A(1)z + A(2)z^2 + A(3)z^3 + ..._  B(0) + B(1)z + B(2)z^2 + B(3)z^3 + ...

    **Properties**:

    .. _ocafilterpolynomial_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.11"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocafilterpolynomial_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocafilterpolynomial_a:

    .. cpp:member:: OcaList<OcaFloat32> A

        Numerator - "A"

        This property has id ``4.1``.

    .. _ocafilterpolynomial_b:

    .. cpp:member:: OcaList<OcaFloat32> B

        Denominator - "B"

        This property has id ``4.2``.

    .. _ocafilterpolynomial_samplerate:

    .. cpp:member:: OcaFrequency SampleRate

        Sample rate inside the filter. We can't assume it's the same as the device input or output rate.

        This property has id ``4.3``.

    .. _ocafilterpolynomial_maxorder:

    .. cpp:member:: const OcaUint8 MaxOrder

        Maximum order of A[] and B[], i.e. the maximum size of the A[] and B[] arrays. Readonly.

        This property has id ``4.4``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocafilterpolynomial_getcoefficients:

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &A, OcaList<OcaFloat32> &B)

        Returns the polynomial coefficients used.

        This method has id ``4.1``.

        :param OcaList<OcaFloat32> A: Output parameter.
        :param OcaList<OcaFloat32> B: Output parameter.

    .. _ocafilterpolynomial_setcoefficients:

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> A, OcaList<OcaFloat32> B)

        Sets the polynomial coefficients.

        This method has id ``4.2``.

        :param OcaList<OcaFloat32> A: Input parameter.
        :param OcaList<OcaFloat32> B: Input parameter.

    .. _ocafilterpolynomial_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the filter sampling rate.

        This method has id ``4.3``.

        :param OcaFrequency Rate: Output parameter.
        :param OcaFrequency minRate: Output parameter.
        :param OcaFrequency maxRate: Output parameter.

    .. _ocafilterpolynomial_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the filter sampling rate.

        This method has id ``4.4``.

        :param OcaFrequency Rate: Input parameter.

    .. _ocafilterpolynomial_getmaxorder:

    .. cpp:function:: OcaStatus GetMaxOrder(OcaUint8 &Order)

        Gets the maximum allowable order (= max number of array elements in numerator and for denominator arrays)

        This method has id ``4.5``.

        :param OcaUint8 Order: Output parameter.


    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


