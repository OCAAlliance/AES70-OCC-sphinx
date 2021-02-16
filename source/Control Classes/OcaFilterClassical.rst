.. _ocafilterclassical:

1.1.1.9  OcaFilterClassical
===========================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFilterClassical: OcaActuator

    A classical analog-style filter - highpass, lowpass, bandpass, etc.,
    with shape characteristics such as Butterworth, Chebyshev, Bessel, and
    Linkwitz-Riley. Frequently used in loudspeaker crossover networks.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaFrequency Frequency

        This property has id ``4.0``.

        The frequency of the filter.

    .. cpp:member:: OcaFilterPassband Passband

        This property has id ``4.0``.

        Lowpass, highpass, bandpass, bandreject

    .. cpp:member:: OcaClassicalFilterShape Shape

        This property has id ``4.0``.

        Shape family - Butterworth, Bessell, etc.

    .. cpp:member:: OcaUint16 Order

        This property has id ``4.0``.

        Filter order

    .. cpp:member:: OcaFloat32 Parameter

        This property has id ``4.0``.

        Ripple or other filter parameter, depending on shape. Not used by some
        shapes.

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        This method has id ``4.1``.

        Gets the value of the Frequency property. The return value indicates
        if the property was successfully retrieved.

        :param OcaFrequency Frequency: Output parameter.
        :param OcaFrequency minFrequency: Output parameter.
        :param OcaFrequency maxFrequency: Output parameter.

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency frequency)

        This method has id ``4.2``.

        Sets the value of the Frequency property. The return value indicates
        if the property was successfully set.

        :param OcaFrequency frequency: Input parameter.

    .. cpp:function:: OcaStatus GetPassband(OcaFilterPassband &Passband)

        This method has id ``4.3``.

        Returns the passband specification of the filter object. The return
        value indicates if the specification was successfully retrieved.

        :param OcaFilterPassband Passband: Output parameter.

    .. cpp:function:: OcaStatus SetPassband(OcaFilterPassband Passband)

        This method has id ``4.4``.

        Sets the passband specification of the filter object. The return value
        indicates if the specification was successfully set.

        :param OcaFilterPassband Passband: Input parameter.

    .. cpp:function:: OcaStatus GetShape(OcaClassicalFilterShape &Shape)

        This method has id ``4.5``.

        Returns the Shape property of the filter. The return value indicates
        if the property was successfully retrieved.

        :param OcaClassicalFilterShape Shape: Output parameter.

    .. cpp:function:: OcaStatus SetShape(OcaClassicalFilterShape Shape)

        This method has id ``4.6``.

        Sets the Shape property of the filter. The return value indicates if
        the property was successfully set.

        :param OcaClassicalFilterShape Shape: Input parameter.

    .. cpp:function:: OcaStatus GetOrder(OcaUint16 &Order, OcaUint16 &minOrder, OcaUint16 &maxOrder)

        This method has id ``4.7``.

        Returns the order of the filter. The return value indicates if the
        property was successfully retrieved.

        :param OcaUint16 Order: Output parameter.
        :param OcaUint16 minOrder: Output parameter.
        :param OcaUint16 maxOrder: Output parameter.

    .. cpp:function:: OcaStatus SetOrder(OcaUint16 Order)

        This method has id ``4.8``.

        Sets the order of the filter. The return value indicates if the
        property was successfully set.

        :param OcaUint16 Order: Input parameter.

    .. cpp:function:: OcaStatus GetParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        This method has id ``4.9``.

        Returns the filter parameter. The return value indicates if the
        property was successfully retrieved.

        :param OcaFloat32 Parameter: Output parameter.
        :param OcaFloat32 minParameter: Output parameter.
        :param OcaFloat32 maxParameter: Output parameter.

    .. cpp:function:: OcaStatus SetParameter(OcaFloat32 Parameter)

        This method has id ``4.10``.

        Sets the filter parameter. The return value indicates if the parameter
        was successfully set.

        :param OcaFloat32 Parameter: Input parameter.

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaFilterPassband Passband, OcaClassicalFilterShape Shape, OcaUint16 Order, OcaFloat32 Parameter)

        This method has id ``4.11``.

        Sets some or all filter parameter. The return value indicates if the
        parameters were successfully set. The action of this method is atomic
        - if any of the value changes fails, none of the changes are made.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaFrequency Frequency: Input parameter.
        :param OcaFilterPassband Passband: Input parameter.
        :param OcaClassicalFilterShape Shape: Input parameter.
        :param OcaUint16 Order: Input parameter.
        :param OcaFloat32 Parameter: Input parameter.

