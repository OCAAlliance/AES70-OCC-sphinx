*******************
Framework Datatypes
*******************

.. _OcaOrganizationID:

OcaOrganizationID
=================

.. cpp:type:: OcaOrganizationID = OcaBlobFixedLen<3>

    Globally unique identifier of an organization. Equal to the organization's
    IEEE OUI or CID. Note that the IEEE defines the OUI space and the CID space
    as disjoint, the this OCA identifier is always completely unique.

.. _OcaClassAuthorityID:

OcaClassAuthorityID
===================

.. cpp:struct:: OcaClassAuthorityID

    Class authority identifier. Identifies the authority for a class's
    definition.

    .. cpp:member:: OcaUint16 Sentinel

        Sentinel signifying an Authority ID

    .. cpp:member:: OcaUint8 Reserved

        Reserved, must be zero.

    .. cpp:member:: OcaOrganizationID OrganizationID

        Authority's IEEE public Company ID (public CID) or IEEE Organizational
        Unique Identifier (OUI), or the value zero, which signifies the
        Authority of this AES70 standard.

.. _OcaClassID:

OcaClassID
==========

.. cpp:type:: OcaClassID

    Class identifier : vector that describes the class's ancestry. The normative
    definition of the Class identifier is given in Part 1 of this standard, in
    the section entitled "Class identifiers". The UML definition given here is
    intended to be identical, but in the case of any discrepancy, Part 1 shall
    be definitive..

.. _OcaVersion:

OcaVersion
==========

.. cpp:struct:: OcaVersion

    Representation of a version number of a (hardware/software) component of a
    device in the form of Major.Minor.Build (e.g. 1.0.123).

    .. cpp:member:: OcaUint32 Major

        The major version number.

    .. cpp:member:: OcaUint32 Minor

        The minor version number.

    .. cpp:member:: OcaUint32 Build

        The build number. May be 0 if it is not used (e.g. for a hardware
        component).

    .. cpp:member:: OcaComponent Component

        The component.

.. _OcaEnumItem:

OcaEnumItem
===========

.. cpp:type:: OcaEnumItem

    The datatype of an enumeration choice.

.. _OcaEnumItem16:

OcaEnumItem16
=============

.. cpp:type:: OcaEnumItem16

    The datatype of an enumeration choice. Long format, used if normal 8-bit
    format isn't going to be big enough.

.. _OcaClassIdentification:

OcaClassIdentification
======================

.. cpp:struct:: OcaClassIdentification


    .. cpp:member:: OcaClassID ClassID


    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Version number of the class.

.. _OcaClassVersionNumber:

OcaClassVersionNumber
=====================

.. cpp:type:: OcaClassVersionNumber = OcaUint16

    Class version number, ascending from **1.**

.. _OcaONo:

OcaONo
======

.. cpp:type:: OcaONo = OcaUint32

    Object number of an OCA object.

.. _OcaOPath:

OcaOPath
========

.. cpp:struct:: OcaOPath

    Object address. Composite of network address in which object resides, and
    object number.

    .. cpp:member:: OcaNetworkHostID HostID

        Host ID of device that contains the referenced object.

    .. cpp:member:: OcaONo ONo

        Object number of referenced object.

.. _OcaNamePath:

OcaNamePath
===========

.. cpp:type:: OcaNamePath = OcaList<OcaString>

    Role-name path from a containing block up to an object. If the containing
    block is the Root Block the path is an absolute path; if not, it is a
    relative path.

.. _OcaONoPath:

OcaONoPath
==========

.. cpp:type:: OcaONoPath = OcaList<OcaONo>

    ONo path from a containing block up to an object. If the containing block is
    the Root Block the path is an absolute path; if not, it is a relative path.

.. _OcaObjectIdentification:

OcaObjectIdentification
=======================

.. cpp:struct:: OcaObjectIdentification

    Object identification. Composite of object number and object's class. Used
    mainly in discovery processes.

    .. cpp:member:: OcaONo ONo

        Object number of referenced object.

    .. cpp:member:: OcaClassIdentification ClassIdentification

        Class identification of referenced object.

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

    Template for complete identification of an OCA property instance, including
    object number, property ID, Get and Set method IDs, and datatype.

    .. cpp:member:: OcaONo ONo

        Object number

    .. cpp:member:: OcaPropertyDescriptor Descriptor

        Property descriptor.

.. _OcaStatus:

OcaStatus
=========

.. cpp:enum:: OcaStatus : uint8_t

    Standard status codes returned from method calls.

    .. cpp:enumerator:: OK = 0


    .. cpp:enumerator:: ProtocolVersionError = 1


    .. cpp:enumerator:: DeviceError = 2


    .. cpp:enumerator:: Locked = 3


    .. cpp:enumerator:: BadFormat = 4


    .. cpp:enumerator:: BadONo = 5


    .. cpp:enumerator:: ParameterError = 6


    .. cpp:enumerator:: ParameterOutOfRange = 7


    .. cpp:enumerator:: NotImplemented = 8


    .. cpp:enumerator:: InvalidRequest = 9


    .. cpp:enumerator:: ProcessingFailed = 10


    .. cpp:enumerator:: BadMethod = 11


    .. cpp:enumerator:: PartiallySucceeded = 12


    .. cpp:enumerator:: Timeout = 13


    .. cpp:enumerator:: BufferOverflow = 14


.. _OcaGlobalTypeIdentifier:

OcaGlobalTypeIdentifier
=======================

.. cpp:struct:: OcaGlobalTypeIdentifier

    Globally unique identifier of something that belongs to an organization.

    .. cpp:member:: OcaOrganizationID Authority

        Unique identifier of organization that has authority over this reusable
        block type. A zero value indicates a global type defined by the AES70
        standard itself.

    .. cpp:member:: OcaUint32 ID

        ID of library volume type defined by given Authority. Value is unique
        within the given Authority.

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

.. _OcaPositionDescriptorFieldFlags:

OcaPositionDescriptorFieldFlags
===============================

.. cpp:type:: OcaPositionDescriptorFieldFlags = OcaBitSet16

    BItset that specifies which fields in **OcaPositionAndOrientation** are
    used. A "1" value signifies that the corresponding
    **OcaPositionAndOrientation** field is used.

.. _OcaPositionDescriptor:

OcaPositionDescriptor
=====================

.. cpp:struct:: OcaPositionDescriptor

    A six-axis c1,c2,c3,c4,c5,c6) coordinate. For mechanical systems, these axes
    shall be interpreted as follows:

     - c1 = X; axial (fore-and-aft) position

     - c2 = Y; lateral (side-to-side) position

     - c3 = Z; vertical position

     - c4 = rX; rotation around the X-axis, also known as *Roll*

     - c5 = rY; rotation around the Y-axis, also known as *Pitch*

     - c6 = rZ; rotation around the Z-axis. also known as *Yaw*


    Rotation angles are measured according to the *right-hand rule:* if the
    right hand "holds" an axis with the thumb pointing in the direction of
    ascending coordinate values, then the fingers point in the direction of
    ascending angle values. For GPS systems, these axes shall be interpreted as
    follows:

     - c1 = longitude

     - c2 = latitude

     - c3 = altitude

     - c4 : not used

     - c5 : not used

     - c6 : not used



    .. cpp:member:: OcaPositionCoordinateSystem CoordinateSystem

        Type of position coordinate system - see AES70-1, section 5.5.9.

    .. cpp:member:: OcaPositionDescriptorFieldFlags FieldFlags

        Which fields of the Values[] array contain valid values.

    .. cpp:member:: OcaFloat32 Values[6]

        The coordinates

.. _OcaPositionCoordinateSystem:

OcaPositionCoordinateSystem
===========================

.. cpp:enum:: OcaPositionCoordinateSystem : uint8_t

    Enumeration that designates the type of position coordinate system used. For
    details, see the AES70-1 description of the **OcaPhysicalPosition** class.

    .. cpp:enumerator:: Robotic = 1

        Six-axis robotic coordinates: {X, Y, Z, rX, rY, rZ} . ``r<axis>`` is
        anticlockwise rotation around the given axis - X, Y, or Z. For details,
        see AES70-1, section 5.5.9.

    .. cpp:enumerator:: ItuAudioObjectBasedPolar = 2

        Object-based audio, polar version, per section 8 of the ITU radio Audio
        Definition Model defined in ITU-R BS.2076-1. For details, see the ITU
        standard and AES70-1, section 5.5.9.

         - Azimuth is angle in the horizontal plane with 0 degrees as straight
           ahead, and positive angles to the left (or anti-clockwise) when
           viewed from above.

         - Elevation is angle in the vertical plane with 0 degrees horizontally
           ahead, and positive angles going up.



    .. cpp:enumerator:: ItuAudioObjectBasedCartesian = 3

        Object-based audio, Cartesian version, per section 8 of the ITU radio
        Audio Definition Model defined in ITU-R BS.2076-1. For details, see the
        ITU standard and AES70-1, section 5.5.9.

    .. cpp:enumerator:: ItuAudioSceneBasedPolar = 4

        Scene-based audio, polar version, per section 8 of the ITU radio Audio
        Definition Model defined in ITU-R BS.2076-1. For details, see the ITU
        standard and AES70-1, section 5.5.9.

    .. cpp:enumerator:: ItuAudioSceneBasedCartesian = 5

        Scene-based audio, Cartesian version, per section 8 of the ITU radio
        Audio Definition Model defined in ITU-R BS.2076-1. For details, see the
        ITU standard and AES70-1, section 5.5.9.

    .. cpp:enumerator:: NAV = 6

        Terrestrial navigation format: {Longitude, Latitude, Altitude}.

    .. cpp:enumerator:: ProprietaryBase = 128

        Base value for proprietary extensions. Proprietary extensions shall be
        numbered starting from this value.

