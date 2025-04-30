*********************************
Miscellaneous Framework Datatypes
*********************************

.. _OcaIODirection:

OcaIODirection
==============

.. cpp:enum:: OcaIODirection : uint8_t

    Enum that describes whether a port is for input or output.

    .. cpp:enumerator:: Input = 1

        Input port

    .. cpp:enumerator:: Output = 2

        Output port

.. _OcaAdaptationData:

OcaAdaptationData
=================

.. cpp:type:: OcaAdaptationData = OcaBlob

    Adaptation-specific data. Typedef of **OcaBlob**; actual format and contents
    depend on the Adaptation. This datatype is equivalent to an **OcaBlob**.
    **OcaBlobs** are containers for contextually-dependent data. Adaptations
    shall assemble this data inside the **OcaBlob** according to a set of
    marshalling rules. In theory, any set of marshaling rules could be used. In
    practice, it is recommended that applications use the marshaling rules of
    OCP.1, the AES70 binary protocol standardized in [AES70-3].

.. _OcaUnitOfMeasure:

OcaUnitOfMeasure
================

.. cpp:enum:: OcaUnitOfMeasure : uint8_t

    Enumeration of units of measure that can be used in OCA classes. Only SI
    (base or derived) units are specified, so that internal calculations will
    not need to convert. If conversion is needed it should only be done in user
    interfaces. The datatype of a reading expressed in one of these units of
    measure is FLOAT.

    .. cpp:enumerator:: Ampere = 4

        Electric current in Amperes.

    .. cpp:enumerator:: DegreeCelsius = 2

        Temperature in degree Celsius.

    .. cpp:enumerator:: Hertz = 1

        Frequency in Hertz.

    .. cpp:enumerator:: None = 0

        No reading.

    .. cpp:enumerator:: Ohm = 5

        Resistance, magnitude of reactance, or magnitude of impedance in Ohms.

    .. cpp:enumerator:: Volt = 3

        Voltage in Volts.

