.. _ocafilterarbitrarycurve:

1.1.1.13  OcaFilterArbitraryCurve
=================================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaFilterArbitraryCurve <ocafilterarbitrarycurve>` 

.. cpp:class:: OcaFilterArbitraryCurve: OcaActuator

    An arbitrary-curve filter, with transfer function specified as amplitude and phase versus frequency.

    **Properties**:

    .. _ocafilterarbitrarycurve_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocafilterarbitrarycurve_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocafilterarbitrarycurve_transferfunction:

    .. cpp:member:: OcaTransferFunction TransferFunction

        Transfer function of the filter.

        This property has id ``4.1``.

    .. _ocafilterarbitrarycurve_samplerate:

    .. cpp:member:: OcaFrequency SampleRate

        Sample rate inside the filter. We can't assume it's the same as the device input or output rate.

        This property has id ``4.2``.

    .. _ocafilterarbitrarycurve_tfminlength:

    .. cpp:member:: OcaUint16 TFMinLength

        Minimum number of points that transfer function must specify

        This property has id ``4.3``.

    .. _ocafilterarbitrarycurve_tfmaxlength:

    .. cpp:member:: OcaUint16 TFMaxLength

        Maximum number of points that transfer function may specify

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

    .. _ocafilterarbitrarycurve_gettransferfunction:

    .. cpp:function:: OcaStatus GetTransferFunction(OcaTransferFunction &TransferFunction)

        Returns the complex transfer function.

        This method has id ``4.1``.

        :param OcaTransferFunction TransferFunction: Output parameter.

    .. _ocafilterarbitrarycurve_settransferfunction:

    .. cpp:function:: OcaStatus SetTransferFunction(OcaTransferFunction TransferFunction)

        Sets the complex transfer function.

        This method has id ``4.2``.

        :param OcaTransferFunction TransferFunction: Input parameter.

    .. _ocafilterarbitrarycurve_getsamplerate:

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        Gets the filter sampling rate.

        This method has id ``4.3``.

        :param OcaFrequency Rate: Output parameter.
        :param OcaFrequency minRate: Output parameter.
        :param OcaFrequency maxRate: Output parameter.

    .. _ocafilterarbitrarycurve_setsamplerate:

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        Sets the filter sampling rate.

        This method has id ``4.4``.

        :param OcaFrequency Rate: Input parameter.

    .. _ocafilterarbitrarycurve_gettfminlength:

    .. cpp:function:: OcaStatus GetTFMinLength(OcaUint16 &Min)

        Returns the minimum number of required points in the specified transfer function.

        This method has id ``4.5``.

        :param OcaUint16 Min: Output parameter.

    .. _ocafilterarbitrarycurve_gettfmaxlength:

    .. cpp:function:: OcaStatus GetTFMaxLength(OcaUint16 &Max)

        Returns the maximum number of allowed points in the specified transfer function.

        This method has id ``4.6``.

        :param OcaUint16 Max: Output parameter.


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
    
    


