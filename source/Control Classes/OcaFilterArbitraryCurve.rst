.. _ocafilterarbitrarycurve:

1.1.1.13  OcaFilterArbitraryCurve
=================================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFilterArbitraryCurve: OcaActuator

    An arbitrary-curve filter, with transfer function specified as
    amplitude and phase versus frequency.

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

    .. cpp:member:: OcaTransferFunction TransferFunction

        This property has id ``4.1``.

        Transfer function of the filter.

    .. cpp:member:: OcaFrequency SampleRate

        This property has id ``4.2``.

        Sample rate inside the filter. We can't assume it's the same as the
        device input or output rate.

    .. cpp:member:: OcaUint16 TFMinLength

        This property has id ``4.3``.

        Minimum number of points that transfer function must specify

    .. cpp:member:: OcaUint16 TFMaxLength

        This property has id ``4.4``.

        Maximum number of points that transfer function may specify

    .. cpp:function:: OcaStatus GetTransferFunction(OcaTransferFunction &TransferFunction)

        This method has id ``4.1``.

        Returns the complex transfer function.

        :param OcaTransferFunction TransferFunction: Output parameter.

    .. cpp:function:: OcaStatus SetTransferFunction(OcaTransferFunction TransferFunction)

        This method has id ``4.2``.

        Sets the complex transfer function.

        :param OcaTransferFunction TransferFunction: Input parameter.

    .. cpp:function:: OcaStatus GetSampleRate(OcaFrequency &Rate, OcaFrequency &minRate, OcaFrequency &maxRate)

        This method has id ``4.3``.

        Gets the filter sampling rate.

        :param OcaFrequency Rate: Output parameter.
        :param OcaFrequency minRate: Output parameter.
        :param OcaFrequency maxRate: Output parameter.

    .. cpp:function:: OcaStatus SetSampleRate(OcaFrequency Rate)

        This method has id ``4.4``.

        Sets the filter sampling rate.

        :param OcaFrequency Rate: Input parameter.

    .. cpp:function:: OcaStatus GetTFMinLength(OcaUint16 &Min)

        This method has id ``4.5``.

        Returns the minimum number of required points in the specified
        transfer function.

        :param OcaUint16 Min: Output parameter.

    .. cpp:function:: OcaStatus GetTFMaxLength(OcaUint16 &Max)

        This method has id ``4.6``.

        Returns the maximum number of allowed points in the specified transfer
        function.

        :param OcaUint16 Max: Output parameter.

