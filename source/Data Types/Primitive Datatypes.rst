*******************
Primitive Datatypes
*******************

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


.. _OcaInt8:

OcaInt8
=======

.. cpp:type:: OcaInt8


.. _OcaInt16:

OcaInt16
========

.. cpp:type:: OcaInt16


.. _OcaInt32:

OcaInt32
========

.. cpp:type:: OcaInt32


.. _OcaInt64:

OcaInt64
========

.. cpp:type:: OcaInt64


.. _OcaUint8:

OcaUint8
========

.. cpp:type:: OcaUint8


.. _OcaUint16:

OcaUint16
=========

.. cpp:type:: OcaUint16


.. _OcaUint32:

OcaUint32
=========

.. cpp:type:: OcaUint32


.. _OcaUint64:

OcaUint64
=========

.. cpp:type:: OcaUint64


.. _OcaFloat32:

OcaFloat32
==========

.. cpp:type:: OcaFloat32


.. _OcaFloat64:

OcaFloat64
==========

.. cpp:type:: OcaFloat64


.. _OcaString:

OcaString
=========

.. cpp:type:: OcaString


.. _OcaBitstring:

OcaBitstring
============

.. cpp:type:: OcaBitstring


.. _OcaBlob:

OcaBlob
=======

.. cpp:type:: OcaBlob


.. _OcaLongBlob:

OcaLongBlob
===========

.. cpp:type:: OcaLongBlob


.. _OcaBlobFixedLen:

OcaBlobFixedLen
===============

.. cpp:struct:: template <typename len> OcaBlobFixedLen<len>


.. _OcaArray1D:

OcaArray1D
==========

.. cpp:struct:: template <typename DT, typename n> OcaArray1D<DT, n>


.. _OcaArray2D:

OcaArray2D
==========

.. cpp:struct:: template <typename DT, typename nX, typename nY> OcaArray2D<DT, nX, nY>


.. _OcaList:

OcaList
=======

.. cpp:struct:: template <typename DT> OcaList<DT>


.. _OcaList32:

OcaList32
=========

.. cpp:struct:: template <typename DT> OcaList32<DT>


.. _OcaList2D:

OcaList2D
=========

.. cpp:struct:: template <typename T> OcaList2D<T>


.. _OcaMap:

OcaMap
======

.. cpp:struct:: template <typename KeyType, typename ValType> OcaMap<KeyType, ValType>


.. _OcaMultiMap:

OcaMultiMap
===========

.. cpp:struct:: template <typename KeyType, typename ValType> OcaMultiMap<KeyType, ValType>


.. _OcaVariant:

OcaVariant
==========

.. cpp:struct:: template <typename elements> OcaVariant<elements>


