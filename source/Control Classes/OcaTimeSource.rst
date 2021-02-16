.. _ocatimesource:

1.2.16  OcaTimeSource
=====================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaTimeSource: OcaAgent

    A time source, internal or external. See RFC 7273 for a detailed
    discussion of time sources.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaTimeSourceAvailability Availability

        This property has id ``3.0``.

        Availability of this time source.

    .. cpp:member:: OcaTimeProtocol Protocol

        This property has id ``3.0``.

        Time transport protocol used by this time source

    .. cpp:member:: OcaSDPString Parameters

        This property has id ``3.0``.

        Parameters (identifiers, modifiers, etc.) for this time source .
        Content is an SDP timestamp reference specification as defined in
        RFC7273, section 4.8.

    .. cpp:member:: OcaTimeReferenceType ReferenceType

        This property has id ``3.0``.

        Type of time reference to which this time source is synced, if any.

    .. cpp:member:: OcaString ReferenceID

        This property has id ``3.0``.

        Identifier of reference to which this time source is synced, if any.
        Not needed for all reference types.

    .. cpp:member:: OcaTimeSourceSyncStatus SyncStatus

        This property has id ``3.0``.

        Synchronization status of this time source.

    .. cpp:function:: OcaStatus GetAvailability(OcaTimeSourceAvailability &Availability)

        This method has id ``3.1``.

        Gets the value of the **Availability** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaTimeSourceAvailability Availability: Output parameter.

    .. cpp:function:: OcaStatus GetProtocol(OcaTimeProtocol &Protocol)

        This method has id ``3.2``.

        Gets the value of the **Protocol** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaTimeProtocol Protocol: Output parameter.

    .. cpp:function:: OcaStatus SetProtocol(OcaTimeProtocol Protocol)

        This method has id ``3.3``.

        Sets the value of the **Protocol** property. The return value
        indicates whether the value was successfully set.

        :param OcaTimeProtocol Protocol: Input parameter.

    .. cpp:function:: OcaStatus GetParameters(OcaSDPString &Parameters)

        This method has id ``3.4``.

        Gets the value of the **Parameters** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaSDPString Parameters: Output parameter.

    .. cpp:function:: OcaStatus SetParameters(OcaSDPString Parameters)

        This method has id ``3.5``.

        Sets the value of the **Parameters** property. The return value
        indicates whether the value was successfully set. Optional method, may
        not be supported in all implementations.

        :param OcaSDPString Parameters: Input parameter.

    .. cpp:function:: OcaStatus GetReferenceType(OcaTimeReferenceType &ReferenceType)

        This method has id ``3.6``.

        Gets the time reference type. The return value indicates whether the
        value was successfully retrieved.

        :param OcaTimeReferenceType ReferenceType: Output parameter.

    .. cpp:function:: OcaStatus SetReferenceType(OcaTimeReferenceType ReferenceType)

        This method has id ``3.7``.

        Sets the time reference type. The return value indicates whether the
        value was successfully set. Optional method, may not be supported in
        all implementations.

        :param OcaTimeReferenceType ReferenceType: Input parameter.

    .. cpp:function:: OcaStatus GetReferenceID(OcaString &ID)

        This method has id ``3.8``.

        Gets the timing source ID. The return value indicates whether the
        value was successfully retrieved. Optional method, not required for
        all time reference types.

        :param OcaString ID: Output parameter.

    .. cpp:function:: OcaStatus SetReferenceID(OcaString ID)

        This method has id ``3.9``.

        Sets the time reference ID. The return value indicates whether the ID
        was successfully set. Optional method, not required for all time
        reference types.

        :param OcaString ID: Input parameter.

    .. cpp:function:: OcaStatus GetSyncStatus(OcaTimeSourceSyncStatus &SyncStatus)

        This method has id ``3.10``.

        Gets the synchronization status of this time source. The return value
        indicates whether the value was successfully retrieved.

        :param OcaTimeSourceSyncStatus SyncStatus: Output parameter.

    .. cpp:function:: OcaStatus Reset()

        This method has id ``3.11``.

        Resets this time source. Initiates a new synchronization sequence. The
        return value indicates whether the reset was successful.


