************************
OcaGroup Event Datatypes
************************

.. _OcaGroupExceptionEventData:

OcaGroupExceptionEventData
==========================

.. cpp:type:: OcaGroupExceptionEventData = OcaList<OcaGroupException>

    Payload of an **OcaGroupException** notification. This datatype is a typedef
    of **OcaList<OcaGroupException>**, q.v.

.. _OcaGroupException:

OcaGroupException
=================

.. cpp:struct:: OcaGroupException

    Member of the OcaGroupExceptionEventData list.

    .. cpp:member:: OcaONo ONo

        ONo of Group Member raising the exception

    .. cpp:member:: OcaMethodID MethodID

        Method ID of the called method that returned a not-OK status, thereby
        causing the exception.

    .. cpp:member:: OcaStatus Status

        Status code returned by the called method.

