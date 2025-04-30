*********************
Time Source Datatypes
*********************

.. _OcaTimeDeliveryMechanism:

OcaTimeDeliveryMechanism
========================

.. cpp:enum:: OcaTimeDeliveryMechanism : uint8_t

    Types of time delivery mechanisms. See [RFC 7273] for a detailed discussion
    of time sources , particularly sections 4.4-4.8. See the various time
    delivery method specifications (e.g. [IEEE-1588] (PTP) [RFC 5905] (NTP)
    [AES11] for more details.

    .. cpp:enumerator:: Undefined = 0

        Time delivery mechanism is undefined.

    .. cpp:enumerator:: Local = 1

        Time reference is inside device..

    .. cpp:enumerator:: Private = 2

        Time delivery mechanism is not a public standard or specification.

    .. cpp:enumerator:: NTP = 3

        Time delivery mechanism is Network Time Protocol. [RFC 5905]

    .. cpp:enumerator:: SNTP = 4

        Time delivery mechanism is Simple Network Time Protocol. [RFC 5905]

    .. cpp:enumerator:: IEEE1588_2002 = 5

        Time delivery mechanism is IEEE1588-2002.

    .. cpp:enumerator:: IEEE1588_2008 = 6

        Time delivery mechanism is IEEE 1588-2008.

    .. cpp:enumerator:: IEEE1588_2019 = 7

        Time delivery mechanism is IEEE 1588-2019.

    .. cpp:enumerator:: IEEE8021AS = 8

        Time delivery mechanism is IEEE 802.1AS, a profile of IEEE 1588-2008.

    .. cpp:enumerator:: StreamEndpoint = 9

        Time delivery mechanism is an internal link to a stream endpoint that
        knows the time. See datatype
        **OcaTimeDeliveryParameters_StreamEndpoint.**

    .. cpp:enumerator:: AES11 = 11

        Time delivery mechanism is AES11. See [AES11].

    .. cpp:enumerator:: TerrestrialRadio = 12

        Time delivery mechanism is a terrestrial radio signal.

    .. cpp:enumerator:: GPS = 13

        Time delivery mechanism is the U.S. Global Positioning System (GPS).

    .. cpp:enumerator:: Galileo = 14

        Time delivery mechanism is the European **Galileo** global positioning
        system.

    .. cpp:enumerator:: GLONASS = 15

        Time delivery mechanism is the Russian **GLONASS** global positioning
        system.

    .. cpp:enumerator:: Beidou = 16

        Time delivery mechanism is the Chinese **Beidou** global positioning
        system.

    .. cpp:enumerator:: INRSS = 17

        Time delivery mechanism is the Indian **INRSS** global positioning
        system.

    .. cpp:enumerator:: ExpansionBase = 128

        Proprietary additions start here.

    .. cpp:enumerator:: None = 1

        Time reference is inside device. **Name chanaged to "Local" in
        AES70-2023.**

    .. cpp:enumerator:: IEEE1588v1 = 5

        Time delivery mechanism is IEEE 1588v1, aka IEEE1588-2002. **Name
        chanaged to** **"IEEE1588_2002" in AES70-2023.**

    .. cpp:enumerator:: IEEE1588v2 = 6

        Time delivery mechanism is IEEE 1588v2, aka IEEE1588-2008. **Name
        chanaged to "IEEE1588_2008" in AES70-2023.**

    .. cpp:enumerator:: IEEE1588v2_1 = 7

        Time delivery mechanism is IEEE 1588v 2.1, aka IEEE1588-2019. **Name
        chanaged to "IEEE1588_2019" in AES70-2023.**

.. _OcaTimeSourceAvailability:

OcaTimeSourceAvailability
=========================

.. cpp:enum:: OcaTimeSourceAvailability : uint8_t

    Availability states of a time source

    .. cpp:enumerator:: Unavailable = 0

        Time source is unavailable.

    .. cpp:enumerator:: Available = 1

        Time source is available.

.. _OcaTimeSourceSyncStatus:

OcaTimeSourceSyncStatus
=======================

.. cpp:enum:: OcaTimeSourceSyncStatus : uint8_t

    Synchronization status of a time source.

    .. cpp:enumerator:: Undefined = 0

        Synchronization state is undefined.

    .. cpp:enumerator:: Unsynchronized = 1

        Time source is not synchronized to reference.

    .. cpp:enumerator:: Synchronizing = 2

        Time source is attempting to synchronize to reference.

    .. cpp:enumerator:: Synchronized = 3

        Time source is synchronized with reference.

.. _OcaTimeDeliveryParameters_StreamEndpoint:

OcaTimeDeliveryParameters_StreamEndpoint
========================================

.. cpp:struct:: OcaTimeDeliveryParameters_StreamEndpoint

    Value of **OcaTimeSource.TimeDeliveryParameters** when
    **OcaTimeSource.DeliveryMechanism** = **StreamEndpoint**. This datatype
    shall be rendered as a JSON object in the parameter record.

    .. cpp:member:: OcaONo EndpointOwner

        ONo of media transport network application object that owns the
        endpoint.

    .. cpp:member:: OcaMediaStreamEndpointID EndpointID

        Endpoint index within its owner.

