************************
Specific Event Datatypes
************************

.. _OcaObjectListEventData:

OcaObjectListEventData
======================

.. cpp:struct:: OcaObjectListEventData

    Notification data supplied by events returning object lists, for example the
    **SynchronizeState** event defined in **OcaSubscriptionManager.**

    .. cpp:member:: OcaList<OcaONo> objectList

        List of object numbers.

.. _OcaEmptyEventData:

OcaEmptyEventData
=================

.. cpp:type:: OcaEmptyEventData

    Empty notification datatype for events with no notification data.

.. _OcaObservationEventData:

OcaObservationEventData
=======================

.. cpp:struct:: OcaObservationEventData

    Notification data supplied by event **OcaNumericObserver.Observation**.
    Note: due to an error in AES70-2015, this class was not made a subclass of
    **OcaEventData**. Therefore, this class explicitly defines the **Event**
    property explicitly, rather than inheriting it from **OcaEventData,** as
    other event data classes do. However, the effect is the same as for all
    event data classes: the first property in the data structure is an
    **OcaEvent** value.

    .. cpp:member:: OcaFloat64 Reading

        The observed value that the event is reporting.

.. _OcaObservationListEventData:

OcaObservationListEventData
===========================

.. cpp:struct:: OcaObservationListEventData

    Notification data supplied by event **OcaNumericObserverList.Observation**.
    Note: due to an error in AES70-2015, this class was not made a subclass of
    **OcaEventData**. Therefore, this class explicitly defines the **Event**
    property explicitly, rather than inheriting it from **OcaEventData,** as
    other event data classes do. However, the effect is the same as for all
    event data classes: the first property in the data structure is an
    **OcaEvent** value.

    .. cpp:member:: OcaList<OcaFloat64> Reading

        The list of observed values that the event is reporting.

.. _OcaCounterUpdateEventData:

OcaCounterUpdateEventData
=========================

.. cpp:struct:: OcaCounterUpdateEventData

    Notification data supplied by **OcaCounterNotifier.CounterUpdate()** event

    .. cpp:member:: OcaList<OcaCounterUpdate> Updates

        List of counter-update descriptors

