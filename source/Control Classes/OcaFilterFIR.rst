.. _ocafilterfir:

1.1.1.12  OcaFilterFIR
======================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFilterFIR: OcaActuator

    A finite impulse response (FIR) filter.

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

    .. cpp:member:: OcaUint32 Length

        This property has id ``4.1``.

        Length of the filter, in samples. Readonly. Value is set when
        SetCoefficients(...) method executes.

    .. cpp:member:: OcaList<OcaFloat32> Coefficients

        This property has id ``4.2``.

        Array of FIR Coefficients. The size of the array (number of entries)
        is equal to the Order property plus 1.

    .. cpp:member:: OcaFrequency SampleRate

        This property has id ``4.3``.

        Sample rate inside the filter. We can't assume it's the same as the
        device input or output rate.

    .. cpp:function:: OcaStatus GetLength(OcaUint32 &Length, OcaUint32 &minLength, OcaUint32 &maxLength)

        This method has id ``4.1``.

        Gets the length of the FIR filter. The return value indicates whether
        the value was successfully retrieved.

        :param OcaUint32 Length: Output parameter.
        :param OcaUint32 minLength: Output parameter.
        :param OcaUint32 maxLength: Output parameter.

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &Coefficients)

        This method has id ``4.2``.

        Gets the coefficients of the FIR filter. The return value indicates
        whether the coefficients were successfully retrieved.

        :param OcaList<OcaFloat32> Coefficients: Output parameter.

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> Coefficients)

        This method has id ``4.3``.

        Sets the value of the properties of the FIR filter. The return value
        indicates whether the properties were successfully set.

        :param OcaList<OcaFloat32> Coefficients: Input parameter.

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        This method has id ``4.4``.

        Gets the sample rate of the FIR filter. The return value indicates
        whether the data was successfully retrieved.

        :param OcaFrequency Rate: Output parameter.
        :param OcaFrequency minRate: Output parameter.
        :param OcaFrequency maxRate: Output parameter.

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        This method has id ``4.5``.

        Sets the sample rate of the FIR filter. The return value indicates
        whether the rate was successfully set.

        :param OcaFrequency Rate: Input parameter.

