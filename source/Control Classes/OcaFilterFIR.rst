.. _ocafilterfir:

1.1.1.12  OcaFilterFIR
======================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaFilterFIR <ocafilterfir>` 

.. cpp:class:: OcaFilterFIR: OcaActuator

    A finite impulse response (FIR) filter.

    **Properties**:

    .. _ocafilterfir_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocafilterfir_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocafilterfir_length:

    .. cpp:member:: OcaUint32 Length

        Length of the filter, in samples. Readonly. Value is set when
        SetCoefficients(...) method executes.

        This property has id ``4.1``.

    .. _ocafilterfir_coefficients:

    .. cpp:member:: OcaList<OcaFloat32> Coefficients

        Array of FIR Coefficients. The size of the array (number of entries)
        is equal to the Order property plus 1.

        This property has id ``4.2``.

    .. _ocafilterfir_samplerate:

    .. cpp:member:: OcaFrequency SampleRate

        Sample rate inside the filter. We can't assume it's the same as the
        device input or output rate.

        This property has id ``4.3``.

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

    .. _ocafilterfir_getlength:

    .. cpp:function:: OcaStatus GetLength(OcaUint32 &Length, OcaUint32 &minLength, OcaUint32 &maxLength)

        Gets the length of the FIR filter. The return value indicates whether
        the value was successfully retrieved.

        This method has id ``4.1``.

        :param OcaUint32 Length: Output parameter.
        :param OcaUint32 minLength: Output parameter.
        :param OcaUint32 maxLength: Output parameter.

    .. _ocafilterfir_getcoefficients:

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &Coefficients)

        Gets the coefficients of the FIR filter. The return value indicates
        whether the coefficients were successfully retrieved.

        This method has id ``4.2``.

        :param OcaList<OcaFloat32> Coefficients: Output parameter.

    .. _ocafilterfir_setcoefficients:

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> Coefficients)

        Sets the value of the properties of the FIR filter. The return value
        indicates whether the properties were successfully set.

        This method has id ``4.3``.

        :param OcaList<OcaFloat32> Coefficients: Input parameter.

    .. _ocafilterfir_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the sample rate of the FIR filter. The return value indicates
        whether the data was successfully retrieved.

        This method has id ``4.4``.

        :param OcaFrequency Rate: Output parameter.
        :param OcaFrequency minRate: Output parameter.
        :param OcaFrequency maxRate: Output parameter.

    .. _ocafilterfir_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the sample rate of the FIR filter. The return value indicates
        whether the rate was successfully set.

        This method has id ``4.5``.

        :param OcaFrequency Rate: Input parameter.


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
    
    


