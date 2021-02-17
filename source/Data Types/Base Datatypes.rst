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
.. _OcaBit:

OcaBit
======

.. cpp:type:: OcaBit = bit

    A single bit.
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

.. cpp:struct:: OcaString
    
    General character string, UTF-8 encoded.

    .. cpp:member:: OcaUint16 Len

        Number of UTF-8 characters in the string.

    .. cpp:member:: string Value

        Unicode string. Encoding is UTF-8.


OCP.1 Encoding
--------------

===== ========== ===========
Field Basic type Byte length
===== ========== ===========
Len   OcaUint16  2          
Value string     variable   
===== ========== ===========


.. _OcaBitstring:

OcaBitstring
============

.. cpp:struct:: OcaBitstring
    
    Representation of a bitmask that is used on the network to send
    bitmask data.

    .. cpp:member:: OcaUint16 NrBits

        The size of the bitmask in bits.

    .. cpp:member:: OcaUint8[] Bitstring

        The bitstring data as an array of bytes with the most significant bit
        of the first byte being bit number 0.


OCP.1 Encoding
--------------

========= ========== ===========
Field     Basic type Byte length
========= ========== ===========
NrBits    OcaUint16  2          
Bitstring OcaUint8   1 * Count  
========= ========== ===========


.. _OcaBlob:

OcaBlob
=======

.. cpp:struct:: OcaBlob
    
    Representation of a binary large object that is used on the network to
    send large chunks of binary data.

    .. cpp:member:: OcaUint16 DataSize

        The size of the BLOB data in bytes.

    .. cpp:member:: OcaUint8[] Data

        The BLOB data.


OCP.1 Encoding
--------------

======== ========== ===========
Field    Basic type Byte length
======== ========== ===========
DataSize OcaUint16  2          
Data     OcaUint8   1 * Count  
======== ========== ===========


.. _OcaBlobFixedLen:

OcaBlobFixedLen
===============

.. cpp:struct:: OcaBlobFixedLen<typename Len>
    
    Template class for fixed-length blob.

    .. cpp:member:: OcaUint8[Len] Value

        The value is an array of bytes with the most significant bit of the
        first byte being bit number 0. Size of the array is determined by the
        template parameter :raw:html:`&lt;`Len:raw:html:`&gt;`.


OCP.1 Encoding
--------------

=============== ==================
Basic type      Byte length       
=============== ==================
OcaBlobFixedLen (0 + 1 * variable)
=============== ==================


.. _OcaList:

OcaList
=======

.. cpp:struct:: OcaList<typename datatype>
    
    Template class representing a list of items.

    .. cpp:member:: OcaUint16 Count

        Number of entries in the list.

    .. cpp:member:: datatype[Count] Items

        The array of items of the list, i.e. each entry placed after each
        other.


OCP.1 Encoding
--------------

========== ======================
Basic type Byte length           
========== ======================
OcaList    (2 + Count * variable)
========== ======================


.. _OcaList2D:

OcaList2D
=========

.. cpp:struct:: OcaList2D<typename datatype>
    
    Template class representing a two-dimensional list of items. This
    class describes only the data, not how it will be marshalled for
    transport via the various OCA protocol implementations.

    .. cpp:member:: OcaUint16 nX

        Number of columns in the list.

    .. cpp:member:: OcaUint16 nY

        Number of rows in the list.

    .. cpp:member:: datatype[nX, nY] Items

        The array of items of the list, i.e. each entry placed after each
        other.


OCP.1 Encoding
--------------

===== ========== ==================
Field Basic type Byte length       
===== ========== ==================
nX    OcaUint16  2                 
nY    OcaUint16  2                 
Items datatype   variable * nX * nY
===== ========== ==================


.. _OcaMapItem:

OcaMapItem
==========

.. cpp:struct:: OcaMapItem<typename KeyDataType, typename ValueDataType>
    
    One element of an **OcaMap** or **OcaMultiMap**

    .. cpp:member:: KeyDataType Key


    .. cpp:member:: ValueDataType Value



OCP.1 Encoding
--------------

===== ============= ===========
Field Basic type    Byte length
===== ============= ===========
Key   KeyDataType   variable   
Value ValueDataType variable   
===== ============= ===========


.. _OcaMap:

OcaMap
======

.. cpp:struct:: OcaMap<typename KeyDataType, typename ValueDataType>
    
    Template class representing a map of keys to values.

    .. cpp:member:: OcaUint16 Count

        Number of entries (key value pairs) in the map.

    .. cpp:member:: OcaMapItem<KeyDataType, ValueDataType>[Count] Items

        The array of items of the map, i.e. each key value pair (value after
        key) placed after each other.


OCP.1 Encoding
--------------

========== ======================
Basic type Byte length           
========== ======================
OcaMap     (2 + Count * variable)
========== ======================


.. _OcaMultiMap:

OcaMultiMap
===========

.. cpp:struct:: OcaMultiMap<typename KeyDataType, typename ValueDataType>
    
    Template _class_ representing a map of keys to values where keys do
    not have to be unique (e.g. can be present multiple times).

    .. cpp:member:: OcaUint16 Count

        Number of entries (key value pairs) in the multimap.

    .. cpp:member:: OcaMapItem<KeyDataType, ValueDataType>[Count] Items

        The array of items of the map, i.e. each key value pair (value after
        key) placed after each other. Note that the keys do not have to be
        unique, i.e. the same key may be present multiple times in the map.


OCP.1 Encoding
--------------

=========== ======================
Basic type  Byte length           
=========== ======================
OcaMultiMap (2 + Count * variable)
=========== ======================

