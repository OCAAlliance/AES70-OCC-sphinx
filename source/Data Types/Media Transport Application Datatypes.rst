*************************************
Media Transport Application Datatypes
*************************************

.. _OcaMediaTransportTimingParameters:

OcaMediaTransportTimingParameters
=================================

.. cpp:struct:: OcaMediaTransportTimingParameters

    Media transport application's transport timing parameters

    .. cpp:member:: OcaTimeInterval MinReceiveBufferCapacity

        Minimum receive buffer capacity in floating-point seconds

    .. cpp:member:: OcaTimeInterval MaxReceiveBufferCapacity

        Maximum receive buffer capacity in floating-point seconds

    .. cpp:member:: OcaTimeInterval TransmissionTimeVariation

        Transmission time variation in floating-point seconds

.. _OcaSDPString:

OcaSDPString
============

.. cpp:type:: OcaSDPString = OcaString

    SDP string compliant with [RFC8866]

