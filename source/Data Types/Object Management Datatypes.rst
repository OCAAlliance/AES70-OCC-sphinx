***************************
Object Management Datatypes
***************************

.. _OcaONo:

OcaONo
======

.. cpp:type:: OcaONo = OcaUint32

    Object number of an OCA object.

.. _OcaRolePath:

OcaRolePath
===========

.. cpp:type:: OcaRolePath = OcaList<OcaString>

    Role Path. See [AES70-1(Text Identification of Control Objects)].

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

