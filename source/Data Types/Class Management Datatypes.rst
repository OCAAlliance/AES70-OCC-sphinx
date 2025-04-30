**************************
Class Management Datatypes
**************************

.. _OcaOrganizationID:

OcaOrganizationID
=================

.. cpp:type:: OcaOrganizationID = OcaBlobFixedLen<3>

    24 bit globally unique identifier of an organization. Equal to the
    organization's IEEE OUI or CID. The OUI namespace and the CID namespace are
    disjoint; thus, the identifier value is always unique. Value of zero
    designates an undefined authority. OCA datatype is a 3-byte
    **OcaBlobFixedLen**

.. _OcaClassID:

OcaClassID
==========

.. cpp:type:: OcaClassID


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

