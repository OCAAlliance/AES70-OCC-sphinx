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

.. _OcaNotificationDeliveryMode:

OcaNotificationDeliveryMode
===========================

.. cpp:enum:: OcaNotificationDeliveryMode : uint8_t

    Enum for subscriptions that specifies whether its notification messages are
    to be delivered by normal means (e.g. TCP) or lightweight means (e.g. UDP).

    .. cpp:enumerator:: Normal = 1

        Normal delivery mode Name was 'Reliable' in AES70-2018 and earlier.

    .. cpp:enumerator:: Lightweight = 2

        Lightweight delivery mode. Name was 'Fast' in AES70-2018 and earlier.

.. _OcaSubscriptionManagerState:

OcaSubscriptionManagerState
===========================

.. cpp:enum:: OcaSubscriptionManagerState : uint8_t

    Enum describing **OcaSubscriptionManager** states.

    .. cpp:enumerator:: Normal = 1


    .. cpp:enumerator:: EventsDisabled = 2

        Events are disabled.

