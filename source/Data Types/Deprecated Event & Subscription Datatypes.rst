*****************************************
Deprecated Event & Subscription Datatypes
*****************************************

.. _OcaMediaConnectorStatusChangedEventData:

OcaMediaConnectorStatusChangedEventData
=======================================

.. cpp:type:: OcaMediaConnectorStatusChangedEventData = OcaMediaConnectorStatus


.. _OcaMediaSourceConnectorChangedEventData:

OcaMediaSourceConnectorChangedEventData
=======================================

.. cpp:struct:: OcaMediaSourceConnectorChangedEventData


    .. cpp:member:: OcaMediaSourceConnector SourceConnector

        The media source connector for which the changed event holds (i.e. that
        is added, deleted or changed).

    .. cpp:member:: OcaPropertyChangeType ChangeType

        Indicates what type of change occurred. Only ItemAdded, ItemChanged and
        ItemDeleted can be used in this event data.

    .. cpp:member:: OcaMediaConnectorElement ChangedElement

        Indicates which element(s) of the connector changed. If the connector is
        added or deleted, all bits in this bitset shall be set.

.. _OcaMediaSinkConnectorChangedEventData:

OcaMediaSinkConnectorChangedEventData
=====================================

.. cpp:struct:: OcaMediaSinkConnectorChangedEventData


    .. cpp:member:: OcaMediaSinkConnector SinkConnector

        The media source connector for which the changed event holds (i.e. that
        is added, deleted or changed).

    .. cpp:member:: OcaPropertyChangeType ChangeType

        Indicates what type of change occurred. Only ItemAdded, ItemChanged and
        ItemDeleted can be used in this event data.

    .. cpp:member:: OcaMediaConnectorElement ChangedElement

        Indicates which element(s) of the connector changed. If the connector is
        added or deleted, all bits in this bitset shall be set.

.. _OcaMediaConnectorElement:

OcaMediaConnectorElement
========================

.. cpp:type:: OcaMediaConnectorElement = OcaBitSet16

    Bitset describing which elements of a media connector have changed.

.. _OcaGrouperStatusChangeType:

OcaGrouperStatusChangeType
==========================

.. cpp:enum:: OcaGrouperStatusChangeType : uint8_t

    Enum describing status change types, as used in **OcaGrouper's
    StatusChange** event. **Deprecated** in AES70-2024.

    .. cpp:enumerator:: citizenAdded = 1

        New citizen has been added to the Grouper and is now in the online
        state.

    .. cpp:enumerator:: citizenDeleted = 2

        A citizen has been deleted from the Grouper.

    .. cpp:enumerator:: citizenConnectionLost = 3

        Previously **online** citizen has lost its connection with the grouper
        and is now in the **offline** state.

    .. cpp:enumerator:: citizenConnectionReEstablished = 4

        Previously **offline** citizen has lost its connection with the grouper
        and is now in the **online** state.

    .. cpp:enumerator:: citizenError = 5

        A citizen has failed to execute a requested parameter change.

    .. cpp:enumerator:: enrollment = 6

        A citizen has enrolled in a group, and is now a **member** of that
        group.

    .. cpp:enumerator:: unEnrollment = 7

        A member has been removed from a group.

.. _OcaGrouperStatusChangeEventData:

OcaGrouperStatusChangeEventData
===============================

.. cpp:struct:: OcaGrouperStatusChangeEventData

    Notification data supplied by the **OcaGrouper.StatusChange()** event.
    **Deprecated** in AES70-2024.

    .. cpp:member:: OcaUint16 groupIndex

        Index of relevant group, or zero if event is non-group-specific.

    .. cpp:member:: OcaUint16 citizenIndex

        Index of citizen within given grouper, or zero if event is
        non-citizen-specific.

    .. cpp:member:: OcaGrouperStatusChangeType changeType

        Type of change.

