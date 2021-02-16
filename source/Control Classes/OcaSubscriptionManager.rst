.. _ocasubscriptionmanager:

1.3.4  OcaSubscriptionManager
=============================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaSubscriptionManager: OcaManager

    Manager that collects and controls the event subscriptions of the
    device.
    
    - Must be instantiated once in every device that supports
    subscriptions.
    
    
    - May be instantiated at most once in any device.
    
    
    - If instantiated, must have object number 4.
    Absence of an **OcaSubscriptionManager** object signifies that the
    device does not support event subscriptions.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaSubscriptionManagerState State

        This property has id ``3.0``.

        Events enabled or disabled. When events are disabled, (1) Only
        notification from the subscription manager itself are sent to
        subscribers, and (2) the subscription manager saves the object numbers
        of all objects that raise events while notifications are disabled. The
        saved numbers are eventually returned by the **SynchronizeState**
        event that occurs when notifications are re-enabled.

    .. cpp:function:: OcaStatus RemoveSubscription(OcaEvent Event, OcaMethod Subscriber)

        This method has id ``3.2``.

        Removes all subscriptions to the given event with the given
        **OcaMethod** . The return value indicates whether the subscription(s)
        was (were) successfully removed.

        :param OcaEvent Event: Input parameter.
        :param OcaMethod Subscriber: Input parameter.

    .. cpp:function:: OcaStatus AddSubscription(OcaEvent Event, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        This method has id ``3.1``.

        Adds a subscription to an event. The subscription is added for the
        session on which the command came in. If a subscription identical to
        the one being requested already exists, an additional one shall not be
        added. Two subscriptions are identical if the **Event, Subscriber,
        NotificationDeliveryMode** , and **DestinationInformation** parameters
        are all identical. The return value indicates whether the subscription
        succeeded.

        :param OcaEvent Event: Input parameter.
        :param OcaMethod Subscriber: Input parameter.
        :param OcaBlob SubscriberContext: Input parameter.
        :param OcaNotificationDeliveryMode NotificationDeliveryMode: Input parameter.
        :param OcaNetworkAddress DestinationInformation: Input parameter.

    .. cpp:function:: OcaStatus DisableNotifications()

        This method has id ``3.3``.

        Temporarily disables emitting of event notifications (to all
        subscribers, not just to the subscriber calling this method). Events
        from the Subscription Manager itself are not disabled. This method can
        be used if either a controller or the local device knows that it is
        going to change the state of the device significantly, which could
        lead to a notification storm of events. Invoking this method will
        prevent the notification storm. The event '03e01 EventsDisabled' will
        be raised to notify all controllers of the fact that events are
        temporarily disabled. The subscription manager will start collecting
        the object numbers of the objects that raise events, so that it can
        pass a list of changed objects once the events are re-enabled. The
        return value indicates if disabling events succeeded.


    .. cpp:function:: OcaStatus ReEnableNotifications()

        This method has id ``3.4``.

        Re-enables the sending of event notifications to all subscribers. When
        events are re-enabled, the subscription manager will raise the
        **SynchronizeState** event, passing the list of objects that have
        changed state. Subsequently, the subscription manager will transmit
        all notifications as normal. If the connection to the controller that
        invoked the DisableEvents() is lost, this method will be called
        automatically to prevent the situation in which the raising of events
        would never be re-enabled. The return value indicates if re-enabling
        the event-based events succeeded.


    .. cpp:function:: OcaStatus AddPropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        This method has id ``3.5``.

        Adds a subscription to the PropertyChanged event in the object Emitter
        for changes of the property Property. If the NotificationDeliveryMode
        is Fast, the subscription is added for the session on which the
        command came in. If a subscription identical to the one being
        requested already exists, an additional one shall not be added. Two
        subscriptions are identical if the Emitter, Property, Subscriber,
        SubsciberContext, NotificationDeliveryMode, and DestinationInformation
        parameters are all identical. The return value indicates whether the
        subscription succeeded. Added in v2 of this class, in AES70-2017.

        :param OcaONo Emitter: Input parameter.
        :param OcaPropertyID Property: Input parameter.
        :param OcaMethod Subscriber: Input parameter.
        :param OcaBlob SubscriberContext: Input parameter.
        :param OcaNotificationDeliveryMode NotificationDeliveryMode: Input parameter.
        :param OcaNetworkAddress DestinationInformation: Input parameter.

    .. cpp:function:: OcaStatus RemovePropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber)

        This method has id ``3.6``.

        Removes any subscription to a PropertyChanged event with the given
        Emitter, Property, Subscriber, SubscriberContext,
        NotificationDeliveryMode, and DestinationInformation. The return value
        indicates whether the subscription(s) was (were) successfully removed.
        Added in v2 of this class, in AES70-2017.

        :param OcaONo Emitter: Input parameter.
        :param OcaPropertyID Property: Input parameter.
        :param OcaMethod Subscriber: Input parameter.

    .. cpp:function:: OcaStatus GetMaximumSubscriberContextLength(OcaUint16 &Max)

        This method has id ``3.7``.

        Returns maximum byte length of payload of subscriber context parameter
        that this device supports. This returned value shall be either zero or
        four. If the returned payload length is not zero, it shall be four. No
        other values shall be allowed, and the returned value shall not change
        once the device has initialized. NOTE: In AES70-2015, arbitrary
        subscriber context lengths were allowed; this is no longer true.

        :param OcaUint16 Max: Output parameter.

