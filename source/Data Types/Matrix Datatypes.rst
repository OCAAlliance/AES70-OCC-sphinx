****************
Matrix Datatypes
****************

.. _OcaMatrixCoordinate:

OcaMatrixCoordinate
===================

.. cpp:type:: OcaMatrixCoordinate = OcaUint16

    Coordinate value (x or y) for **OcaMatrix. ** Value is zero-relative, i.e.
    the first row or column is number zero. A value of 65535 means all rows or
    columns.

.. _OcaMatrixCommand:

OcaMatrixCommand
================

.. cpp:struct:: OcaMatrixCommand

    (X,Y) of a Matrix Member. X=column, Y=row. Zero-relative: X=0 is first
    column, Y=0 is first row.

    .. cpp:member:: OcaMatrixCoordinates Coordinates

        Coordinates of method owner's Matrix Member. First column and first row
        are numbered zero.

    .. cpp:member:: OcaMethodID ID

        ID of the method

    .. cpp:member:: OcaList<OcaLongBlob> Parameters

        Command parameters, if any. Format is method-specific.

.. _OcaMatrixCoordinates:

OcaMatrixCoordinates
====================

.. cpp:struct:: OcaMatrixCoordinates

    (X,Y) of a Matrix Member. X=column, Y=row. Zero-relative: X=0 is first
    column, Y=0 is first row.

    .. cpp:member:: OcaMatrixCoordinate X

        Column index of Matrix Member. First column is numbered zero.

    .. cpp:member:: OcaMatrixCoordinate Y

        Row index of Matrix Member. First row is numbered zero.

