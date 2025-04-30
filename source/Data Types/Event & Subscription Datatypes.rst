******************************
Event & Subscription Datatypes
******************************

.. _OcaEvent:

OcaEvent
========

.. cpp:struct:: OcaEvent

    Representation of an OCA event, i.e. the unique combination of emitter ONo
    and the EventID.

    .. cpp:member:: OcaONo EmitterONo

        Object number of the emitter.

    .. cpp:member:: OcaEventID EventID

        Event ID of the subscribed event.

.. _OcaMethod:

OcaMethod
=========

.. cpp:struct:: OcaMethod

    Representation of an OCA method, i.e. the unique combination of an ONo and a
    MethodID. To denote the absence of a method, all field values shall be zero.
    Such a value is called the *Null Method Identifier*.

    .. cpp:member:: OcaONo ONo

        The object number. For Null Method Identifier, value shall be zero.

    .. cpp:member:: OcaMethodID MethodID

        The method ID. For Null Method Identifier, value of all subfields shall
        be zero.

.. _OcaEventData:

OcaEventData
============

.. cpp:type:: OcaEventData = OcaEvent

    Base class for event data. This base class holds the event data that every
    event notification must contain. When an event has additional properties,
    these propeties shall be defined in a class defined as a subclass of this
    base class. The properties of this base class need not be restated in the
    property list of the subclass, since they will be included by inheritance.

.. _OcaLibVolChangedEventData:

OcaLibVolChangedEventData
=========================

.. cpp:struct:: OcaLibVolChangedEventData

    Event data for the **OcaLibVolChanged** event, which signals a change in an
    **OcaLibrary.Volumes** property.

    .. cpp:member:: OcaLibVolID VolumeID

        ID of library volume that changed.

    .. cpp:member:: OcaPropertyChangeType ChangeType

        Type of change : Will be either itemChanged, itemAdded, or itemDeleted.

.. _OcaPropertyChangedEventData:

OcaPropertyChangedEventData
===========================

.. cpp:struct:: OcaPropertyChangedEventData

    Template class that defines the event data parameter for events that return
    property values, such as the **PropertyChanged** event defined in
    **OcaRoot**, and the **PeriodicObservation** event define in
    **OcaNumericObserver.** The template parameter is the datatype of the
    changed property.

    .. cpp:member:: OcaPropertyID PropertyID

        The property ID of the property that has changed.

    .. cpp:member:: variant PropertyValue

        New value of property. Type of property value parameter is defined by
        template parameter DataType. In the case of list and map properties with
        datatypes such as OcaList, OcaList2D, OcaMap, and OcaMultiMap, the
        entire list or map shall be returned when any of its elements changes.

    .. cpp:member:: OcaPropertyChangeType ChangeType

        Type of change : Current value, Min, Max, Item changed, Item added, Item
        deleted

.. _OcaPropertyChangeType:

OcaPropertyChangeType
=====================

.. cpp:enum:: OcaPropertyChangeType : uint8_t

    Enum describing property change type.

    .. cpp:enumerator:: CurrentChanged = 1

        Current value has changed.

    .. cpp:enumerator:: MinChanged = 2

        Minimum value has changed.

    .. cpp:enumerator:: MaxChanged = 3

        Maximum value has changed.

    .. cpp:enumerator:: ItemAdded = 4

        An item has been added to a list or a map property.

    .. cpp:enumerator:: ItemChanged = 5

        An item of a list or a map property has been changed.

    .. cpp:enumerator:: ItemDeleted = 6

        An item of a list or a map property has been deleted.

.. _OcaMediaConnectorElement:

OcaMediaConnectorElement
========================

.. cpp:type:: OcaMediaConnectorElement = OcaBitSet16

    Bitset describing which elements of a media connector have changed.

.. _OcaMediaConnectorStatusChangedEventData:

OcaMediaConnectorStatusChangedEventData
=======================================

.. cpp:struct:: OcaMediaConnectorStatusChangedEventData


    .. cpp:member:: OcaMediaConnectorStatus ConnectorStatus

        The status that has changed.

.. _OcaTaskStateChangedEventData:

OcaTaskStateChangedEventData
============================

.. cpp:struct:: OcaTaskStateChangedEventData


    .. cpp:member:: OcaTaskID TaskID

        ID of Task

    .. cpp:member:: OcaLibVolIdentifier ProgramID

        Library volume identifier of Program running in the task at the time of
        the change, or null

    .. cpp:member:: OcaTaskStatus Status

        New task status

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

.. _OcaObjectListEventData:

OcaObjectListEventData
======================

.. cpp:struct:: OcaObjectListEventData

    Event data for events returning object lists, for example the
    **SynchronizeState** event defined in **OcaSubscriptionManager.**

    .. cpp:member:: OcaList<OcaONo> objectList

        List of object numbers.

.. _OcaObservationEventData:

OcaObservationEventData
=======================

.. cpp:struct:: OcaObservationEventData

    Event data for event **OcaNumericObserver.Observation**. Note: due to an
    error in AES70-2015, this class was not made a subclass of **OcaEventData**.
    Therefore, this class explicitly defines the **Event** property explicitly,
    rather than inheriting it from **OcaEventData,** as other event data classes
    do. However, the effect is the same as for all event data classes: the first
    property in the data structure is an **OcaEvent** value.

    .. cpp:member:: OcaFloat64 Reading

        The observed value that the event is reporting.

.. _OcaObservationListEventData:

OcaObservationListEventData
===========================

.. cpp:struct:: OcaObservationListEventData

    Event data for event **OcaNumericObserverList.Observation**. Note: due to an
    error in AES70-2015, this class was not made a subclass of **OcaEventData**.
    Therefore, this class explicitly defines the **Event** property explicitly,
    rather than inheriting it from **OcaEventData,** as other event data classes
    do. However, the effect is the same as for all event data classes: the first
    property in the data structure is an **OcaEvent** value.

    .. cpp:member:: OcaList<OcaFloat64> Reading

        The list of observed values that the event is reporting.

.. _OcaGrouperStatusChangeType:

OcaGrouperStatusChangeType
==========================

.. cpp:enum:: OcaGrouperStatusChangeType : uint8_t

    Enum describing status change types, as used in **OcaGrouper's
    StatusChange** event.

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

    Class that defines the event data parameter for the **StatusChange** event
    defined in **OcaGrouper**.

    .. cpp:member:: OcaUint16 groupIndex

        Index of relevant group, or zero if event is non-group-specific.

    .. cpp:member:: OcaUint16 citizenIndex

        Index of citizen within given grouper, or zero if event is
        non-citizen-specific.

    .. cpp:member:: OcaGrouperStatusChangeType changeType

        Type of change.

.. _OcaNotificationDeliveryMode:

OcaNotificationDeliveryMode
===========================

.. cpp:enum:: OcaNotificationDeliveryMode : uint8_t

    Enum for subscriptions that specifies whether its notification messages are
    to be delivered by reliable means (e.g. TCP) or fast means (e.g. UDP).

    .. cpp:enumerator:: Reliable = 1

        Reliable delivery mode, e.g. TCP.

    .. cpp:enumerator:: Fast = 2

        Fast delivery mode, e.g. UDP.

.. _OcaSubscriptionManagerState:

OcaSubscriptionManagerState
===========================

.. cpp:enum:: OcaSubscriptionManagerState : uint8_t

    Enum describing **OcaSubscriptionManager** states.

    .. cpp:enumerator:: Normal = 1


    .. cpp:enumerator:: EventsDisabled = 2

        Events are disabled.

