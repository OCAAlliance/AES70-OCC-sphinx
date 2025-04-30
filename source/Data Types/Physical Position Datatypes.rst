***************************
Physical Position Datatypes
***************************

.. _OcaPositionDescriptorFieldFlags:

OcaPositionDescriptorFieldFlags
===============================

.. cpp:type:: OcaPositionDescriptorFieldFlags = OcaBitSet16

    BItset that specifies which fields in **OcaPositionAndOrientation** are
    used. A "1" value shall signify that the corresponding
    **OcaPositionAndOrientation** field is used.

.. _OcaPositionDescriptor:

OcaPositionDescriptor
=====================

.. cpp:struct:: OcaPositionDescriptor

    A six-axis (c1,c2,c3,c4,c5,c6) coordinate. For mechanical systems, these
    axes shall be interpreted as follows:

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

    .. cpp:member:: OcaArray1D<OcaFloat32, 6> Values

        The coordinates

.. _OcaPositionCoordinateSystem:

OcaPositionCoordinateSystem
===========================

.. cpp:enum:: OcaPositionCoordinateSystem : uint8_t

    Enumeration that designates the type of position coordinate system used. For
    details, see the AES70-1 description of the **OcaPhysicalPosition** class.

    .. cpp:enumerator:: Robotic = 1

        Six-axis robotic coordinates: {X, Y, Z, rX, rY, rZ} . ``r<axis>`` shall
        be anticlockwise rotation around the given axis - X, Y, or Z. For
        details, see AES70-1, section 5.5.9.

    .. cpp:enumerator:: ItuAudioObjectBasedPolar = 2

        Object-based audio, polar version, per section 8 of the ITU radio Audio
        Definition Model defined in ITU-R BS.2076-1. For details, see the ITU
        standard and AES70-1, section 5.5.9.

         - Azimuth shall be angle in the horizontal plane with 0 degrees as
           straight ahead, and positive angles to the left (or anti-clockwise)
           when viewed from above.

         - Elevation shall be angle in the vertical plane with 0 degrees
           horizontally ahead, and positive angles going up.



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

