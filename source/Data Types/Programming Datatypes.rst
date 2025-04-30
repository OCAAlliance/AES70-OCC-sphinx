*********************
Programming Datatypes
*********************

.. _OcaEnumItem:

OcaEnumItem
===========

.. cpp:type:: OcaEnumItem = OcaUint8

    The datatype of an enumeration choice.

.. _OcaBitSet16:

OcaBitSet16
===========

.. cpp:type:: OcaBitSet16 = OcaUint16

    **OcaBitSet16** shall define a 16-bit integer that represents a set of 16
    bits. Each bit shall be represented by one binary digit of a 16-bit number.
    In this standard, each bit of a bitset is defined by a static constant
    attribute with the value of its 16-bit integer representation. For example,
    consider a bitset datatype **MyColor** that represents three colors **Red**,
    **Green**, and **Blue**. Its static attributes would be defined as follows:
    MyColor Red value=1 MyColor Green value=2 MyColor Blue value=4

.. _OcaEnumItem16:

OcaEnumItem16
=============

.. cpp:type:: OcaEnumItem16 = OcaUint16

    The datatype of an enumeration choice. Long format, used if normal 8-bit
    format isn't going to be big enough.

.. _OcaID16:

OcaID16
=======

.. cpp:type:: OcaID16 = OcaUint16

    Generic type for 16-bit IDs and handles. Values should not be reused unless
    device is reset. If no new values remain, values may be reused, but the
    algorithm for choosing reused values is implementation-dependent.

.. _OcaID32:

OcaID32
=======

.. cpp:type:: OcaID32 = OcaUint32

    Generic type for 32-bit IDs and handles. Values should not be reused unless
    device is reset. If no new values remain, values may be reused, but the
    algorithm for choosing reused values is implementation-dependent.

.. _OcaJsonValue:

OcaJsonValue
============

.. cpp:type:: OcaJsonValue = OcaString

    A data value serialized according to the JSON encoding rules defined in
    [AES70-2(JSON encoding)].

.. _OcaParameterRecord:

OcaParameterRecord
==================

.. cpp:type:: OcaParameterRecord = OcaJsonValue

    A parameter record. JSON object that represents a parameter data set defined
    by an external (i.e. non-OCA) protocol. Instructions for use are in
    [AES70-2(Parameter Records)].

.. _OcaAdaptationIdentifier:

OcaAdaptationIdentifier
=======================

.. cpp:type:: OcaAdaptationIdentifier = OcaString

    String constrained to follow the syntax of c identifiers:

     - Only alphanumerics and underscore

     - Must not start with number

     - Names starting with "oca" in any character case are reserved for AES use.



.. _OcaUUID:

OcaUUID
=======

.. cpp:type:: OcaUUID = OcaString

    UUID per [RFC 4122]

.. _OcaMimeType:

OcaMimeType
===========

.. cpp:type:: OcaMimeType = OcaString

    MIME 'CONTENT-TYPE' value as defined in RFC 2045, section 5. See the
    [AES70-1] annex "MIME Media type" for an explanation.

.. _OcaParameterMask:

OcaParameterMask
================

.. cpp:type:: OcaParameterMask = OcaBitSet16

    Bitset to indicate which method parameters contain valid data. The position
    of a bit in the bitset shall correspond to the ordinal position of the
    respective parameter of the method in question.

.. _OcaStringComparisonType:

OcaStringComparisonType
=======================

.. cpp:enum:: OcaStringComparisonType : uint8_t

    Type of string comparison.

    .. cpp:enumerator:: Exact = 0

        Exact comparison, Case-sensitive.

    .. cpp:enumerator:: Substring = 1

        Match all strings whose initial substrings equal the given key.
        Case-sensitive.

    .. cpp:enumerator:: Contains = 2

        Match all strings that contain the given key. Case-sensitive.

    .. cpp:enumerator:: ExactCaseInsensitive = 3

        Exact comparison. Case-insensitive.

    .. cpp:enumerator:: SubstringCaseInsensitive = 4

        Match all strings whose initial substrings equal the given key.
        Case-insensitive.

    .. cpp:enumerator:: ContainsCaseInsensitive = 5

        Match all strings that contain the given key. Case-insensitive.

.. _OcaRelationalOperator:

OcaRelationalOperator
=====================

.. cpp:enum:: OcaRelationalOperator : uint8_t

    Enumeration of relational operators that can be used in OCA classes.

    .. cpp:enumerator:: None = 0


    .. cpp:enumerator:: Equality = 1

        The equality (==) operator.

    .. cpp:enumerator:: Inequality = 2

        The inequality (!=) operator.

    .. cpp:enumerator:: GreaterThan = 3

        The greater than ``(>)`` operator.

    .. cpp:enumerator:: GreaterThanOrEqual = 4

        The greater than or equal ``(>=)`` operator.

    .. cpp:enumerator:: LessThan = 5

        The less than ``(<)`` operator

    .. cpp:enumerator:: LessThanOrEqual = 6

        The less than or equal ``(<=)`` operator.

.. _OcaInterval:

OcaInterval
===========

.. cpp:struct:: template <typename DT> OcaInterval<DT>

    Template datatype that expresses a range of values according to the
    mathematical definition of "interval". An interval consists of one or two
    values called "bounds".

     - An interval with two bounds (an upper and a lower) is called "bounded".

     - An interval with only one bound is called "half-bounded".


    A bound may be "inclusive" or "exclusive".

     - An inclusive bound includes its value in the interval.

     - An exclusive bound excludes its value from the interval.

     - Inclusive bounds are usually indicated by "[ ]" delimiters, exclusive
       bounds by "( )" or "][".


    For example:

     - [5,10] includes all values V such that 5 ``<=`` V ``<=`` 10.

     - (5,10) includes all values V such that 5 ``<`` V ``<`` 10.

     - [5,10) includes all values V such that 5 ``<=`` V ``<`` 10.

     - (5,10] includes all values V such that 5 ``<`` V ``<=`` 10.


    Here are some half-bounded intervals:

     - [5,) and [5,] mean all values V such that 5 ``<=`` V.

     - (5,) and (5,] mean all values V such that 5 ``<`` V.

     - (,10] and [,10] mean all values V such that V ``<=`` 10.

     - (,10) and [,10) mean all values V such that V ``<`` 10.


    When a datatype (e.g. **OcaFloat32**, **OcaFloat64**) has a value ("**inf**"
    below) to represent Infinity, it may be used as a bound. For example:

     - [1.0, **inf**) means all values V such that 1.0 ``<=`` V and V ``<``
       **inf**

     - [1.0,** inf**] means all values V such that 1.0 ``<=`` V

     - (**-inf**, 1.0] means all values V such that V ``<=`` 1.0 and V ``>``
       **-inf**

     - [**-inf**, 1.0] means all values V such that V ``<=`` 1.0


    ... and so on. The usual term "range" means an inclusive, bounded interval,
    e.g. "the range from 3 to 12" means [3,12]. The property **.Bounds** is a
    bitset that specifies which bounds are given and whether the given bounds
    are inclusive or exclusive. **OcaInterval** is a **template** datatype,
    where the template variable is the datatype of the bounds. Thus, may be
    defined for integers, floats, and even strings.

.. _OcaIntervalBounds:

OcaIntervalBounds
=================

.. cpp:type:: OcaIntervalBounds = OcaBitSet16

    Bitset describing which bounds of an **OcaInterval** have been specified,
    and whether each specified bound is inclusive or exclusive. Bitset values
    have the following meanings: **MinOmitted**: 0 if Min is specified, 1 if
    omitted **MaxOmitted**: 0 if Max is specified, 1 if omitted
    **MinInclusive**: 0 if Min is an exclusive bound, 1 if inclusive
    **MaxInclusive**: 0 if Max is an exclusive bound, 1 if inclusive Thus , for
    **OcaInterval** = **{Min, Max, Bounds}**, and where a means any bit value -
    1 or 0 x means any number Q designates the quantity under test: {x,x,0b0000}
    = empty interval {x,x,0baa11} = whole number line {10,40,0b0000} = 10 ``<``
    Q ``<`` 40 {10,40,0b1100} = 10 ``<=`` Q ``<=`` 40 {10,x,0ba110} = 10 ``<=``
    Q {10,x,0ba010} = 10 ``<`` Q

.. _OcaTypedBlob:

OcaTypedBlob
============

.. cpp:struct:: OcaTypedBlob

    **OcaBlob** with ancillary field that shall specify the MIME type of the
    **OcaBlob's** content.

    .. cpp:member:: OcaMimeType ContentType

        MIME type of the content of the **Content** field.

    .. cpp:member:: OcaBlob Content

        **OcaBlob** whose payload has the format specified by the
        **ContentType** field.

