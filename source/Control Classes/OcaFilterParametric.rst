.. _ocafilterparametric:

1.1.1.10  OcaFilterParametric
=============================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFilterParametric: OcaActuator

    A parametric equalizer section with various shape options.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaFrequency Frequency

        This property has id ``4.1``.

        The frequency setpoint of the parametric filter.

    .. cpp:member:: OcaParametricEQShape Shape

        This property has id ``4.2``.

        The shape of the parametric filter - peak, shelf, etc.

    .. cpp:member:: OcaFloat32 WidthParameter

        This property has id ``4.3``.

        Width parameter. For normal parametric implementations, this is the Q
        of the filter.

    .. cpp:member:: OcaDB InbandGain

        This property has id ``4.4``.

        In-band gain of the parametric filter.

    .. cpp:member:: OcaFloat32 ShapeParameter

        This property has id ``4.5``.

        Width parameter. For certain filter types, this parameter may be used
        to represent extra information about the shape of the transfer
        function.

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        This method has id ``4.1``.

        Gets the equalizer frequency setpoint. The return value indicates
        whether the data was successfully retrieved.

        :param OcaFrequency Frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency Frequency)

        This method has id ``4.2``.

        Sets the equalizer frequency. The return value indicates whether the
        value was successfully set.

        :param OcaFrequency Frequency: Input parameter.

    .. cpp:function:: OcaStatus GetShape(OcaParametricEQShape &type)

        This method has id ``4.3``.

        Gets the curve shape of the equalizer. The return value indicates
        whether the data was successfully retrieved.

        :param OcaParametricEQShape type: Output parameter.

    .. cpp:function:: OcaStatus SetShape(OcaParametricEQShape type)

        This method has id ``4.4``.

        Sets the curve shape shape of the equalizer. The return value
        indicates whether the shape was successfully set.

        :param OcaParametricEQShape type: Input parameter.

    .. cpp:function:: OcaStatus GetWidthParameter(OcaFloat32 &Width, OcaFloat32 &minWidth, OcaFloat32 &maxWidth)

        This method has id ``4.5``.

        Gets the width parameter property of the equalizer. The return value
        indicates whether the data was successfully retrieved.

        :param OcaFloat32 Width: Output parameter.
        :param OcaFloat32 minWidth: Output parameter.
        :param OcaFloat32 maxWidth: Output parameter.

    .. cpp:function:: OcaStatus SetWidthParameter(OcaFloat32 Width)

        This method has id ``4.6``.

        Sets the width parameter property of the equalizer. The return value
        indicates whether the Q was successfully set.

        :param OcaFloat32 Width: Input parameter.

    .. cpp:function:: OcaStatus GetInbandGain(OcaDB &gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``4.7``.

        Returns the in-band gain of the equalizer. The return value indicates
        whether the data was successfully retrieved.

        :param OcaDB gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. cpp:function:: OcaStatus SetInbandGain(OcaDB gain)

        This method has id ``4.8``.

        Sets the in-band gain of the equalizer. The return value indicates
        whether the gain was successfully set.

        :param OcaDB gain: Input parameter.

    .. cpp:function:: OcaStatus GetShapeParameter(OcaFloat32 &shape, OcaFloat32 &minShape, OcaFloat32 &maxShape)

        This method has id ``4.9``.

        Returns the shape parameter of the equalizer. The return value
        indicates whether the data was successfully retrieved.

        :param OcaFloat32 shape: Output parameter.
        :param OcaFloat32 minShape: Output parameter.
        :param OcaFloat32 maxShape: Output parameter.

    .. cpp:function:: OcaStatus SetShapeParameter(OcaFloat32 shape)

        This method has id ``4.10``.

        Sets the shape parameter of the equalizer. The return value indicates
        whether the parameter was successfully set.

        :param OcaFloat32 shape: Input parameter.

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaParametricEQShape Shape, OcaFloat32 WidthParameter, OcaDB InBandGain, OcaFloat32 ShapeParameter)

        This method has id ``4.11``.

        Sets some or all filter parameters. The return value indicates if the
        parameters were successfully set. The action of this method is atomic
        - if any of the value changes fails, none of the changes are made.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency: Input parameter.
        :param OcaParametricEQShape Shape: Input parameter.
        :param OcaFloat32 WidthParameter: Input parameter.
        :param OcaDB InBandGain: Input parameter.
        :param OcaFloat32 ShapeParameter: Input parameter.

