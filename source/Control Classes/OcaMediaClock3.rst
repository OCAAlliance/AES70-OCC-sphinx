.. _ocamediaclock3:

1.2.15  OcaMediaClock3
======================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaMediaClock3: OcaAgent

    A media clock, internal or external. OCA Connection Management 3
    (OCA-CM3) version.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaMediaClockAvailability Availability

        This property has id ``3.1``.

        Availability of media clock.

    .. cpp:member:: OcaONo TimeSourceONo

        This property has id ``3.2``.

        ONo of time source that drives this media clock.

    .. cpp:member:: OcaTimePTP Offset

        This property has id ``3.3``.

        Offset of media clock time from reference time. Note: For RTP-based
        media transport networks, this value is NOT the RTP time offset. RTP
        time offset is an implementation detail that is out of AES70's scope.

    .. cpp:member:: OcaMediaClockRate CurrentRate

        This property has id ``3.4``.

        Current clock rate

    .. cpp:member:: OcaMap<OcaONo, OcaList> SupportedRates

        This property has id ``3.5``.

        Map of supported rates for each supported time source. Key of map is
        ONo of supported time source; value is list of supported clock rates
        for the given time source. Private parameter, does not generate
        property-change events.

    .. cpp:function:: OcaStatus GetAvailability(OcaMediaClockAvailability &Availability)

        This method has id ``3.1``.

        Gets the value of the **Availability** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaMediaClockAvailability Availability: Output parameter.

    .. cpp:function:: OcaStatus SetAvailability(OcaMediaClockAvailability Availability)

        This method has id ``3.2``.

        Sets the value of the **Availability** property. The return value
        indicates whether the value was successfully set. Optional method, may
        not be supported in all implementations.

        :param OcaMediaClockAvailability Availability: Input parameter.

    .. cpp:function:: OcaStatus GetCurrentRate(OcaMediaClockRate &Rate, OcaONo &TimeSourceONo)

        This method has id ``3.3``.

        Gets the current clock rate and the ONo of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully retrieved.

        :param OcaMediaClockRate Rate: Output parameter.
        :param OcaONo TimeSourceONo: Output parameter.

    .. cpp:function:: OcaStatus SetCurrentRate(OcaMediaClockRate Rate, OcaONo TimeSourceONo)

        This method has id ``3.4``.

        Sets the clock rate and the ONo of the associated **OcaTimeSource**
        object. The return value indicates whether the value was successfully
        set. Optional method, may not be supported in all implementations.

        :param OcaMediaClockRate Rate: Input parameter.
        :param OcaONo TimeSourceONo: Input parameter.

    .. cpp:function:: OcaStatus GetOffset(OcaTimePTP &Offset)

        This method has id ``3.5``.

        Gets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully retrieved.

        :param OcaTimePTP Offset: Output parameter.

    .. cpp:function:: OcaStatus SetOffset(OcaTimePTP Offset)

        This method has id ``3.6``.

        Sets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully set. Optional method, may not be supported in all
        implementations.

        :param OcaTimePTP Offset: Input parameter.

    .. cpp:function:: OcaStatus GetSupportedRates(OcaMap<OcaONo, OcaList> &Rates)

        This method has id ``3.7``.

        Gets the list of supported media clock rates for the given time
        source. The return value indicates whether the list was successfully
        retrieved.

        :param OcaMap<OcaONo, OcaList> Rates: Output parameter.

