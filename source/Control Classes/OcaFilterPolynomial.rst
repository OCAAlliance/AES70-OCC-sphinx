.. _ocafilterpolynomial:

1.1.1.11  OcaFilterPolynomial
=============================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaFilterPolynomial: OcaActuator

    A generic Z-domain rational polynomial filter section: _A(0) + A(1)z +
    A(2)z^2 + A(3)z^3 + ..._ B(0) + B(1)z + B(2)z^2 + B(3)z^3 + ...

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

    .. cpp:member:: OcaList<OcaFloat32> A

        This property has id ``4.0``.

        Numerator - "A"

    .. cpp:member:: OcaList<OcaFloat32> B

        This property has id ``4.0``.

        Denominator - "B"

    .. cpp:member:: OcaFrequency SampleRate

        This property has id ``4.0``.

        Sample rate inside the filter. We can't assume it's the same as the
        device input or output rate.

    .. cpp:member:: OcaUint8 MaxOrder

        This property has id ``4.0``.

        Maximum order of A[] and B[], i.e. the maximum size of the A[] and B[]
        arrays. Readonly.

    .. cpp:function:: OcaStatus GetCoefficients(OcaList<OcaFloat32> &A, OcaList<OcaFloat32> &B)

        This method has id ``4.1``.

        Returns the polynomial coefficients used.

        :param OcaList<OcaFloat32> A: Output parameter.
        :param OcaList<OcaFloat32> B: Output parameter.

    .. cpp:function:: OcaStatus SetCoefficients(OcaList<OcaFloat32> A, OcaList<OcaFloat32> B)

        This method has id ``4.2``.

        Sets the polynomial coefficients.

        :param OcaList<OcaFloat32> A: Input parameter.
        :param OcaList<OcaFloat32> B: Input parameter.

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

    .. cpp:function:: OcaStatus GetMaxOrder(OcaUint8 &Order)

        This method has id ``4.5``.

        Gets the maximum allowable order (= max number of array elements in
        numerator and for denominator arrays)

        :param OcaUint8 Order: Output parameter.

