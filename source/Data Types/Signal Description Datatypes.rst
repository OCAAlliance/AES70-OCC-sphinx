****************************
Signal Description Datatypes
****************************

.. _OcaDB:

OcaDB
=====

.. cpp:type:: OcaDB = OcaFloat32

    A ratio expressed in dB. Typically used for gain settings.

.. _OcaDBr:

OcaDBr
======

.. cpp:struct:: OcaDBr

    An absolute level expressed in dB above the given absolute reference level.

    .. cpp:member:: OcaDB Value

        Absolute level in decibels relative to value of **Ref** property.

    .. cpp:member:: OcaDBz Ref

        Reference level in dBz. See the definition of OcaDBz for an explanation
        of the dBz unit.

.. _OcaDBV:

OcaDBV
======

.. cpp:type:: OcaDBV = OcaDB

    An absolute analogue level expressed in dB re 1 volt. This datatype may only
    be used for parameters that reflect analogue signal values, e.g. pre-ADC
    input signals and post-DAC output signals.

.. _OcaDBu:

OcaDBu
======

.. cpp:type:: OcaDBu = OcaDB

    An absolute analogue level expressed in dB re 0.774 volts. This datatype may
    only be used for parameters that reflect analogue signal values, e.g.
    pre-ADC input signals and post-DAC output signals.

.. _OcaDBFS:

OcaDBFS
=======

.. cpp:type:: OcaDBFS = OcaDB

    An absolute level value for digital signals, expressed in dB relative to the
    device maximum internal digital sample value. For example, a digital signal
    whose peak sample value is 7dB below the maximum digital sample value shall
    be said to have a peak level of -7 dBFS.

.. _OcaDBz:

OcaDBz
======

.. cpp:type:: OcaDBz = OcaDB

    An absolute level expressed in dB relative to the nominal device operating
    level. The nominal device operating level is a device-specific signal level
    chosen as a normal or typical signal amplitude for the device.

.. _OcaVoltage:

OcaVoltage
==========

.. cpp:type:: OcaVoltage = OcaFloat32

    Voltage in volts.

.. _OcaCurrent:

OcaCurrent
==========

.. cpp:type:: OcaCurrent = OcaFloat32

    Current in amperes

.. _OcaFrequency:

OcaFrequency
============

.. cpp:type:: OcaFrequency = OcaFloat32

    Frequency in Hertz.

.. _OcaPresentationUnit:

OcaPresentationUnit
===================

.. cpp:enum:: OcaPresentationUnit : uint8_t

    Enumeration of presentation units that can be used in OCA classes. Property
    values of OCA objects are always in SI units (unless explicitly documented
    otherwise), but the presentation unit can also be stored to indicate in
    which unit the value was presented in a user interface. This way another
    controller can also present it in that unit (i.e. doing a conversion on the
    controller before presenting it) to keep the user presentation uniform. Note
    that the presentation unit may be equal to the unit of the property (in
    which case of course no conversion is needed).

    .. cpp:enumerator:: dBu = 0

        dB(0.775 VRMS) - voltage relative to 0.775 volts.

    .. cpp:enumerator:: dBV = 1

        dB(1 VRMS) - voltage relative to 1 volt.

    .. cpp:enumerator:: V = 2

        Voltage in plain volts.

