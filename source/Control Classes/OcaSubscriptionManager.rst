.. _ocasubscriptionmanager:

1.3.4  OcaSubscriptionManager
=============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaSubscriptionManager <ocasubscriptionmanager>` 

.. cpp:class:: OcaSubscriptionManager: OcaManager

    Manager that collects and controls the event subscriptions of the
    device.
    
    - Must be instantiated once in every device that supports
    subscriptions.
    
    
    - May be instantiated at most once in any device.
    
    
    - If instantiated, must have object number 4.
    Absence of an **OcaSubscriptionManager** object signifies that the
    device does not support event subscriptions.

    **Properties**:

    .. _ocasubscriptionmanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocasubscriptionmanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocasubscriptionmanager_state:

    .. cpp:member:: OcaSubscriptionManagerState State

        Events enabled or disabled. When events are disabled, (1) Only
        notification from the subscription manager itself are sent to
        subscribers, and (2) the subscription manager saves the object numbers
        of all objects that raise events while notifications are disabled. The
        saved numbers are eventually returned by the **SynchronizeState**
        event that occurs when notifications are re-enabled.

        This property has id ``3.1``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocasubscriptionmanager_removesubscription:

    .. cpp:function:: OcaStatus RemoveSubscription(OcaEvent Event, OcaMethod Subscriber)

        Removes all subscriptions to the given event with the given
        **OcaMethod** . The return value indicates whether the subscription(s)
        was (were) successfully removed.

        This method has id ``3.2``.

        :param OcaEvent Event: Input parameter.
        :param OcaMethod Subscriber: Input parameter.

    .. _ocasubscriptionmanager_addsubscription:

    .. cpp:function:: OcaStatus AddSubscription(OcaEvent Event, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds a subscription to an event. The subscription is added for the
        session on which the command came in. If a subscription identical to
        the one being requested already exists, an additional one shall not be
        added. Two subscriptions are identical if the **Event, Subscriber,
        NotificationDeliveryMode** , and **DestinationInformation** parameters
        are all identical. The return value indicates whether the subscription
        succeeded.

        This method has id ``3.1``.

        :param OcaEvent Event: Input parameter.
        :param OcaMethod Subscriber: Input parameter.
        :param OcaBlob SubscriberContext: Input parameter.
        :param OcaNotificationDeliveryMode NotificationDeliveryMode: Input parameter.
        :param OcaNetworkAddress DestinationInformation: Input parameter.

    .. _ocasubscriptionmanager_disablenotifications:

    .. cpp:function:: OcaStatus DisableNotifications()

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

        This method has id ``3.3``.


    .. _ocasubscriptionmanager_reenablenotifications:

    .. cpp:function:: OcaStatus ReEnableNotifications()

        Re-enables the sending of event notifications to all subscribers. When
        events are re-enabled, the subscription manager will raise the
        **SynchronizeState** event, passing the list of objects that have
        changed state. Subsequently, the subscription manager will transmit
        all notifications as normal. If the connection to the controller that
        invoked the DisableEvents() is lost, this method will be called
        automatically to prevent the situation in which the raising of events
        would never be re-enabled. The return value indicates if re-enabling
        the event-based events succeeded.

        This method has id ``3.4``.


    .. _ocasubscriptionmanager_addpropertychangesubscription:

    .. cpp:function:: OcaStatus AddPropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds a subscription to the PropertyChanged event in the object Emitter
        for changes of the property Property. If the NotificationDeliveryMode
        is Fast, the subscription is added for the session on which the
        command came in. If a subscription identical to the one being
        requested already exists, an additional one shall not be added. Two
        subscriptions are identical if the Emitter, Property, Subscriber,
        SubsciberContext, NotificationDeliveryMode, and DestinationInformation
        parameters are all identical. The return value indicates whether the
        subscription succeeded. Added in v2 of this class, in AES70-2017.

        This method has id ``3.5``.

        :param OcaONo Emitter: Input parameter.
        :param OcaPropertyID Property: Input parameter.
        :param OcaMethod Subscriber: Input parameter.
        :param OcaBlob SubscriberContext: Input parameter.
        :param OcaNotificationDeliveryMode NotificationDeliveryMode: Input parameter.
        :param OcaNetworkAddress DestinationInformation: Input parameter.

    .. _ocasubscriptionmanager_removepropertychangesubscription:

    .. cpp:function:: OcaStatus RemovePropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber)

        Removes any subscription to a PropertyChanged event with the given
        Emitter, Property, Subscriber, SubscriberContext,
        NotificationDeliveryMode, and DestinationInformation. The return value
        indicates whether the subscription(s) was (were) successfully removed.
        Added in v2 of this class, in AES70-2017.

        This method has id ``3.6``.

        :param OcaONo Emitter: Input parameter.
        :param OcaPropertyID Property: Input parameter.
        :param OcaMethod Subscriber: Input parameter.

    .. _ocasubscriptionmanager_getmaximumsubscribercontextlength:

    .. cpp:function:: OcaStatus GetMaximumSubscriberContextLength(OcaUint16 &Max)

        Returns maximum byte length of payload of subscriber context parameter
        that this device supports. This returned value shall be either zero or
        four. If the returned payload length is not zero, it shall be four. No
        other values shall be allowed, and the returned value shall not change
        once the device has initialized. NOTE: In AES70-2015, arbitrary
        subscriber context lengths were allowed; this is no longer true.

        This method has id ``3.7``.

        :param OcaUint16 Max: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
