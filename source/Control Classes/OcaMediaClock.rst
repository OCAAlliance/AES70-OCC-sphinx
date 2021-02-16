.. _ocamediaclock:

1.2.6  OcaMediaClock
====================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaMediaClock: OcaAgent

    **DEPRECATED CLASS** *Replaced by* **OcaMediaClock3** A media clock,
    internal or external.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaMediaClockType Type

        This property has id ``3.0``.

        Type of clock.

    .. cpp:member:: OcaUint16 DomainID

        This property has id ``3.0``.

        Clock domain ID. Arbitrary value.

    .. cpp:member:: OcaList<OcaMediaClockRate> RatesSupported

        This property has id ``3.0``.

        List of supported rates

    .. cpp:member:: OcaMediaClockRate CurrentRate

        This property has id ``3.0``.

        Current clock rate

    .. cpp:member:: OcaMediaClockLockState LockState

        This property has id ``3.0``.

        Lock state of clock.

    .. cpp:function:: OcaStatus GetType(OcaMediaClockType &Type)

        This method has id ``3.1``.

        Gets the value of the **Type** property. The return value indicates
        whether the value was successfully retrieved.

        :param OcaMediaClockType Type: Output parameter.

    .. cpp:function:: OcaStatus SetType(OcaMediaClockType Type)

        This method has id ``3.2``.

        Sets the value of the **Type** property. The return value indicates
        whether the value was successfully set. Optional method, may not be
        supported in all implementations.

        :param OcaMediaClockType Type: Input parameter.

    .. cpp:function:: OcaStatus GetDomainID(OcaUint16 &ID)

        This method has id ``3.3``.

        Gets the value of the **DomainID** property. The return value
        indicates whether the value was successfully retrieved.

        :param OcaUint16 ID: Output parameter.

    .. cpp:function:: OcaStatus SetDomainID(OcaUint16 ID)

        This method has id ``3.4``.

        Sets the value of the **DomainID** property. The return value
        indicates whether the value was successfully set. Optional method, may
        not be supported in all implementations.

        :param OcaUint16 ID: Input parameter.

    .. cpp:function:: OcaStatus GetSupportedRates(OcaList<OcaMediaClockRate> &ID)

        This method has id ``3.5``.

        Gets the list of supported sampling rates. The return value indicates
        whether the list was successfully retrieved.

        :param OcaList<OcaMediaClockRate> ID: Output parameter.

    .. cpp:function:: OcaStatus GetCurrentRate(OcaMediaClockRate &rate)

        This method has id ``3.6``.

        Gets the current sampling rate. The return value indicates whether the
        value was successfully retrieved.

        :param OcaMediaClockRate rate: Output parameter.

    .. cpp:function:: OcaStatus SetCurrentRate(OcaMediaClockRate rate)

        This method has id ``3.7``.

        Sets the sampling rate. The return value indicates whether the rate
        was successfully set.

        :param OcaMediaClockRate rate: Input parameter.

    .. cpp:function:: OcaStatus GetLockState(OcaMediaClockLockState &state)

        This method has id ``3.8``.

        Gets the current media clock lock state. The return value indicates
        whether the value was successfully retrieved.

        :param OcaMediaClockLockState state: Output parameter.

