***********************
Class Element Datatypes
***********************

.. _OcaMethodID:

OcaMethodID
===========

.. cpp:struct:: OcaMethodID

    Representation of an OCA method ID. A class may define at most 255 methods
    of its own. Additional methods may be inherited, so the total number may
    exceed 255.

    .. cpp:member:: OcaUint16 DefLevel

        Level in tree of class which defines this method (1=root)

    .. cpp:member:: OcaUint16 MethodIndex

        Index of the method (in the class description).

.. _OcaPropertyID:

OcaPropertyID
=============

.. cpp:struct:: OcaPropertyID

    Representation of an OCA property ID. A class may define at most 255
    properties of its own. Additional properties may be inherited, so the total
    number may exceed 255.

    .. cpp:member:: OcaUint16 DefLevel

        Level in tree of class which defines this property (1=root)

    .. cpp:member:: OcaUint16 PropertyIndex

        Index of the property (in the class description).

.. _OcaEventID:

OcaEventID
==========

.. cpp:struct:: OcaEventID

    Representation of an OCA event ID. A class may define at most 255 events of
    its own. Additional events may be inherited, so the total number may exceed
    255.

    .. cpp:member:: OcaUint16 DefLevel

        Level in tree of class which defines this event (1=root)

    .. cpp:member:: OcaUint16 EventIndex

        Index of the event (in the class description).

.. _OcaPropertyDescriptor:

OcaPropertyDescriptor
=====================

.. cpp:struct:: OcaPropertyDescriptor

    Description of an OCA property, including property ID, Get and Set method
    IDs, and datatype.

    .. cpp:member:: OcaPropertyID PropertyID


    .. cpp:member:: OcaBaseDataType BaseDataType

        The base datatype of the property. Chosen from an enum datatype that
        represents the available set of basedatatypes**.**

    .. cpp:member:: OcaMethodID GetterMethodID

        Method ID of GET method

    .. cpp:member:: OcaMethodID SetterMethodID

        Method ID of SET method

.. _OcaProperty:

OcaProperty
===========

.. cpp:struct:: OcaProperty

    Identification of an OCA property instance, including object number,
    property ID, Get and Set method IDs, and datatype.

    .. cpp:member:: OcaONo ONo

        Object number

    .. cpp:member:: OcaPropertyDescriptor Descriptor

        Property descriptor.

