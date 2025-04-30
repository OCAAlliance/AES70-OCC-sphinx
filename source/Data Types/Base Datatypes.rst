**************
Base Datatypes
**************

.. _OcaBaseDataType:

OcaBaseDataType
===============

.. cpp:enum:: OcaBaseDataType : uint8_t

    Enum that describes all available base datatypes.

    .. cpp:enumerator:: None = 0

        Undefined

    .. cpp:enumerator:: OcaBoolean = 1

        Generic boolean

    .. cpp:enumerator:: OcaInt8 = 2

        Generic UINT8

    .. cpp:enumerator:: OcaInt16 = 3

        Generic UINT16

    .. cpp:enumerator:: OcaInt32 = 4

        Generic UINT32

    .. cpp:enumerator:: OcaInt64 = 5

        Generic UINT64

    .. cpp:enumerator:: OcaUint8 = 6

        Generic UINT8

    .. cpp:enumerator:: OcaUint16 = 7

        Generic UINT16

    .. cpp:enumerator:: OcaUint32 = 8

        Generic UINT32

    .. cpp:enumerator:: OcaUint64 = 9

        Generic UINT64

    .. cpp:enumerator:: OcaFloat32 = 10

        Generic 32 bit float

    .. cpp:enumerator:: OcaFloat64 = 11

        Generic 64 bit float

    .. cpp:enumerator:: OcaString = 12

        Character count + character array (UTF8)

    .. cpp:enumerator:: OcaBitstring = 13

        Bit count + bit array

    .. cpp:enumerator:: OcaBlob = 14

        Byte count + byte array

    .. cpp:enumerator:: OcaBlobFixedLen = 15

        Byte array

    .. cpp:enumerator:: OcaBit = 16

        One bit

.. _OcaBoolean:

OcaBoolean
==========

.. cpp:type:: OcaBoolean

    True or false

.. _OcaInt8:

OcaInt8
=======

.. cpp:type:: OcaInt8

    Generic 8 bit integer parameter

.. _OcaInt16:

OcaInt16
========

.. cpp:type:: OcaInt16

    Generic integer parameter

.. _OcaInt32:

OcaInt32
========

.. cpp:type:: OcaInt32

    Generic long integer parameter

.. _OcaInt64:

OcaInt64
========

.. cpp:type:: OcaInt64

    Generic long integer parameter

.. _OcaUint8:

OcaUint8
========

.. cpp:type:: OcaUint8

    General-purpose short index

.. _OcaUint16:

OcaUint16
=========

.. cpp:type:: OcaUint16

    General-purpose short index

.. _OcaUint32:

OcaUint32
=========

.. cpp:type:: OcaUint32


.. _OcaUint64:

OcaUint64
=========

.. cpp:type:: OcaUint64

    Generic unsigned 64-bit integer parameter

.. _OcaFloat32:

OcaFloat32
==========

.. cpp:type:: OcaFloat32

    Generic 64-bit IEEE floating-point parameter

.. _OcaFloat64:

OcaFloat64
==========

.. cpp:type:: OcaFloat64

    Generic 64-bit IEEE floating-point parameter

.. _OcaString:

OcaString
=========

.. cpp:type:: OcaString

    General character string, UTF-8 encoded.

.. _OcaBitstring:

OcaBitstring
============

.. cpp:type:: OcaBitstring

    Representation of a bitmask that is used on the network to send bitmask
    data.

.. _OcaBlob:

OcaBlob
=======

.. cpp:type:: OcaBlob

    Representation of a binary large object that is used on the network to send
    large chunks of binary data.

.. _OcaBlobFixedLen:

OcaBlobFixedLen
===============

.. cpp:struct:: template <typename len> OcaBlobFixedLen<len>

    Template class for fixed-length blob.

.. _OcaList:

OcaList
=======

.. cpp:struct:: template <typename DT> OcaList<DT>

    Template class representing a list of items.

.. _OcaList2D:

OcaList2D
=========

.. cpp:struct:: template <typename T> OcaList2D<T>

    Template class representing a two-dimensional list of items. This class
    describes only the data, not how it will be marshalled for transport via the
    various OCA protocol implementations.

.. _OcaMap:

OcaMap
======

.. cpp:struct:: template <typename KeyType, typename ValType> OcaMap<KeyType, ValType>

    Template class representing a map of keys to values.

.. _OcaMultiMap:

OcaMultiMap
===========

.. cpp:struct:: template <typename KeyType, typename ValType> OcaMultiMap<KeyType, ValType>

    Template class representing a map of keys to values where keys do not have
    to be unique (e.g. can be present multiple times).

