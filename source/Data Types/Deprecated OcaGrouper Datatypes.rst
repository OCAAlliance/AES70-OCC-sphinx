*******************************
Deprecated OcaGrouper Datatypes
*******************************

.. _OcaGrouperGroup:

OcaGrouperGroup
===============

.. cpp:struct:: OcaGrouperGroup

    Describes a Group in a Grouper. **Deprecated** in AES70-2024.

    .. cpp:member:: OcaUint16 Index

        Index of Group in Grouper

    .. cpp:member:: OcaString Name

        Name of Group

    .. cpp:member:: OcaONo ProxyONo

        Object Number of the Group's Proxy. The Proxy's class shall be the same
        as the Grouper's Citizen Class.

.. _OcaGrouperCitizen:

OcaGrouperCitizen
=================

.. cpp:struct:: OcaGrouperCitizen

    Describes a Citizen of a Grouper. Refers to a specific Worker object
    somewhere in the media network. **Deprecated** in AES70-2024.

    .. cpp:member:: OcaUint16 Index

        Index of Citizen in Grouper

    .. cpp:member:: OcaOPath ObjectPath

        Object Path (= hostname + Object Number) of the Worker object that is
        the Citizen of the Grouper.

    .. cpp:member:: OcaBoolean Online

        True if and only if connection from Grouper to Citizen is healthy.

.. _OcaGrouperEnrollment:

OcaGrouperEnrollment
====================

.. cpp:struct:: OcaGrouperEnrollment

    Describes the Enrollment of a Citizen in a Group. **Deprecated** in
    AES70-2024.

    .. cpp:member:: OcaUint16 GroupIndex

        Index of Group in which the given Citizen identified is enrolled.

    .. cpp:member:: OcaUint16 CitizenIndex


.. _OcaGrouperMode:

OcaGrouperMode
==============

.. cpp:enum:: OcaGrouperMode : uint8_t

    Select mode of **OcaGrouper**: hierarchical or peer-to-peer. **Deprecated**
    in AES70-2024.

    .. cpp:enumerator:: Hierarchical = 1

        OcaGrouper is in hierarchical mode.

    .. cpp:enumerator:: PeerToPeer = 2

        OcaGrouper is in peer-to-peer mode.

