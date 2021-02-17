.. _ocafilterparametric:

1.1.1.10  OcaFilterParametric
=============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaFilterParametric <ocafilterparametric>` 

.. cpp:class:: OcaFilterParametric: OcaActuator

    A parametric equalizer section with various shape options.

    **Properties**:

    .. _ocafilterparametric_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocafilterparametric_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocafilterparametric_frequency:

    .. cpp:member:: OcaFrequency Frequency

        The frequency setpoint of the parametric filter.

        This property has id ``4.1``.

    .. _ocafilterparametric_shape:

    .. cpp:member:: OcaParametricEQShape Shape

        The shape of the parametric filter - peak, shelf, etc.

        This property has id ``4.2``.

    .. _ocafilterparametric_widthparameter:

    .. cpp:member:: OcaFloat32 WidthParameter

        Width parameter. For normal parametric implementations, this is the Q
        of the filter.

        This property has id ``4.3``.

    .. _ocafilterparametric_inbandgain:

    .. cpp:member:: OcaDB InbandGain

        In-band gain of the parametric filter.

        This property has id ``4.4``.

    .. _ocafilterparametric_shapeparameter:

    .. cpp:member:: OcaFloat32 ShapeParameter

        Width parameter. For certain filter types, this parameter may be used
        to represent extra information about the shape of the transfer
        function.

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

    .. _ocafilterparametric_getfrequency:

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the equalizer frequency setpoint. The return value indicates
        whether the data was successfully retrieved.

        This method has id ``4.1``.

        :param OcaFrequency Frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. _ocafilterparametric_setfrequency:

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency Frequency)

        Sets the equalizer frequency. The return value indicates whether the
        value was successfully set.

        This method has id ``4.2``.

        :param OcaFrequency Frequency: Input parameter.

    .. _ocafilterparametric_getshape:

    .. cpp:function:: OcaStatus GetShape(OcaParametricEQShape &type)

        Gets the curve shape of the equalizer. The return value indicates
        whether the data was successfully retrieved.

        This method has id ``4.3``.

        :param OcaParametricEQShape type: Output parameter.

    .. _ocafilterparametric_setshape:

    .. cpp:function:: OcaStatus SetShape(OcaParametricEQShape type)

        Sets the curve shape shape of the equalizer. The return value
        indicates whether the shape was successfully set.

        This method has id ``4.4``.

        :param OcaParametricEQShape type: Input parameter.

    .. _ocafilterparametric_getwidthparameter:

    .. cpp:function:: OcaStatus GetWidthParameter(OcaFloat32 &Width, OcaFloat32 &minWidth, OcaFloat32 &maxWidth)

        Gets the width parameter property of the equalizer. The return value
        indicates whether the data was successfully retrieved.

        This method has id ``4.5``.

        :param OcaFloat32 Width: Output parameter.
        :param OcaFloat32 minWidth: Output parameter.
        :param OcaFloat32 maxWidth: Output parameter.

    .. _ocafilterparametric_setwidthparameter:

    .. cpp:function:: OcaStatus SetWidthParameter(OcaFloat32 Width)

        Sets the width parameter property of the equalizer. The return value
        indicates whether the Q was successfully set.

        This method has id ``4.6``.

        :param OcaFloat32 Width: Input parameter.

    .. _ocafilterparametric_getinbandgain:

    .. cpp:function:: OcaStatus GetInbandGain(OcaDB &gain, OcaDB &minGain, OcaDB &maxGain)

        Returns the in-band gain of the equalizer. The return value indicates
        whether the data was successfully retrieved.

        This method has id ``4.7``.

        :param OcaDB gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. _ocafilterparametric_setinbandgain:

    .. cpp:function:: OcaStatus SetInbandGain(OcaDB gain)

        Sets the in-band gain of the equalizer. The return value indicates
        whether the gain was successfully set.

        This method has id ``4.8``.

        :param OcaDB gain: Input parameter.

    .. _ocafilterparametric_getshapeparameter:

    .. cpp:function:: OcaStatus GetShapeParameter(OcaFloat32 &shape, OcaFloat32 &minShape, OcaFloat32 &maxShape)

        Returns the shape parameter of the equalizer. The return value
        indicates whether the data was successfully retrieved.

        This method has id ``4.9``.

        :param OcaFloat32 shape: Output parameter.
        :param OcaFloat32 minShape: Output parameter.
        :param OcaFloat32 maxShape: Output parameter.

    .. _ocafilterparametric_setshapeparameter:

    .. cpp:function:: OcaStatus SetShapeParameter(OcaFloat32 shape)

        Sets the shape parameter of the equalizer. The return value indicates
        whether the parameter was successfully set.

        This method has id ``4.10``.

        :param OcaFloat32 shape: Input parameter.

    .. _ocafilterparametric_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaParametricEQShape Shape, OcaFloat32 WidthParameter, OcaDB InBandGain, OcaFloat32 ShapeParameter)

        Sets some or all filter parameters. The return value indicates if the
        parameters were successfully set. The action of this method is atomic
        - if any of the value changes fails, none of the changes are made.

        This method has id ``4.11``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency: Input parameter.
        :param OcaParametricEQShape Shape: Input parameter.
        :param OcaFloat32 WidthParameter: Input parameter.
        :param OcaDB InBandGain: Input parameter.
        :param OcaFloat32 ShapeParameter: Input parameter.


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
    
    
