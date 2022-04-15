.. _ocafilterclassical:

1.1.1.9  OcaFilterClassical
===========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaFilterClassical <ocafilterclassical>` 

.. cpp:class:: OcaFilterClassical: OcaActuator

    A classical analog-style filter - highpass, lowpass, bandpass, etc., with shape characteristics such as Butterworth, Chebyshev, Bessel, and Linkwitz-Riley. Frequently used in loudspeaker crossover networks.

    **Properties**:

    .. _ocafilterclassical_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.9"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocafilterclassical_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocafilterclassical_frequency:

    .. cpp:member:: OcaFrequency Frequency

        The frequency of the filter.

        This property has id ``4.1``.

    .. _ocafilterclassical_passband:

    .. cpp:member:: OcaFilterPassband Passband

        Lowpass, highpass, bandpass, bandreject

        This property has id ``4.2``.

    .. _ocafilterclassical_shape:

    .. cpp:member:: OcaClassicalFilterShape Shape

        Shape family - Butterworth, Bessell, etc.

        This property has id ``4.3``.

    .. _ocafilterclassical_order:

    .. cpp:member:: OcaUint16 Order

        Filter order

        This property has id ``4.4``.

    .. _ocafilterclassical_parameter:

    .. cpp:member:: OcaFloat32 Parameter

        Ripple or other filter parameter, depending on shape. Not used by some shapes.

        This property has id ``4.5``.

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

    .. _ocafilterclassical_getfrequency:

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency property. The return value indicates if the property was successfully retrieved.

        This method has id ``4.1``.

        :param OcaFrequency Frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. _ocafilterclassical_setfrequency:

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency frequency)

        Sets the value of the Frequency property. The return value indicates if the property was successfully set.

        This method has id ``4.2``.

        :param OcaFrequency frequency: Input parameter.

    .. _ocafilterclassical_getpassband:

    .. cpp:function:: OcaStatus GetPassband(OcaFilterPassband &Passband)

        Returns the passband specification of the filter object. The return value indicates if the specification was successfully retrieved.

        This method has id ``4.3``.

        :param OcaFilterPassband Passband: Output parameter.

    .. _ocafilterclassical_setpassband:

    .. cpp:function:: OcaStatus SetPassband(OcaFilterPassband Passband)

        Sets the passband specification of the filter object. The return value indicates if the specification was successfully set.

        This method has id ``4.4``.

        :param OcaFilterPassband Passband: Input parameter.

    .. _ocafilterclassical_getshape:

    .. cpp:function:: OcaStatus GetShape(OcaClassicalFilterShape &Shape)

        Returns the Shape property of the filter. The return value indicates if the property was successfully retrieved.

        This method has id ``4.5``.

        :param OcaClassicalFilterShape Shape: Output parameter.

    .. _ocafilterclassical_setshape:

    .. cpp:function:: OcaStatus SetShape(OcaClassicalFilterShape Shape)

        Sets the Shape property of the filter. The return value indicates if the property was successfully set.

        This method has id ``4.6``.

        :param OcaClassicalFilterShape Shape: Input parameter.

    .. _ocafilterclassical_getorder:

    .. cpp:function:: OcaStatus GetOrder(OcaUint16 &Order, OcaUint16 &minOrder, OcaUint16 &maxOrder)

        Returns the order of the filter. The return value indicates if the property was successfully retrieved.

        This method has id ``4.7``.

        :param OcaUint16 Order: Output parameter.
        :param OcaUint16 minOrder: Output parameter.
        :param OcaUint16 maxOrder: Output parameter.

    .. _ocafilterclassical_setorder:

    .. cpp:function:: OcaStatus SetOrder(OcaUint16 Order)

        Sets the order of the filter. The return value indicates if the property was successfully set.

        This method has id ``4.8``.

        :param OcaUint16 Order: Input parameter.

    .. _ocafilterclassical_getparameter:

    .. cpp:function:: OcaStatus GetParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        Returns the filter parameter. The return value indicates if the property was successfully retrieved.

        This method has id ``4.9``.

        :param OcaFloat32 Parameter: Output parameter.
        :param OcaFloat32 minParameter: Output parameter.
        :param OcaFloat32 maxParameter: Output parameter.

    .. _ocafilterclassical_setparameter:

    .. cpp:function:: OcaStatus SetParameter(OcaFloat32 Parameter)

        Sets the filter parameter. The return value indicates if the parameter was successfully set.

        This method has id ``4.10``.

        :param OcaFloat32 Parameter: Input parameter.

    .. _ocafilterclassical_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaFilterPassband Passband, OcaClassicalFilterShape Shape, OcaUint16 Order, OcaFloat32 Parameter)

        Sets some or all filter parameter. The return value indicates if the parameters were successfully set. The action of this method is atomic - if any of the value changes fails, none of the changes are made.

        This method has id ``4.11``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency: Input parameter.
        :param OcaFilterPassband Passband: Input parameter.
        :param OcaClassicalFilterShape Shape: Input parameter.
        :param OcaUint16 Order: Input parameter.
        :param OcaFloat32 Parameter: Input parameter.


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
    
    


