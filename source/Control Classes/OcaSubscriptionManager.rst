.. _ocasubscriptionmanager:

1.3.4  OcaSubscriptionManager
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaSubscriptionManager <ocasubscriptionmanager>`

.. cpp:class:: OcaSubscriptionManager: OcaManager

    Manager that collects and controls the event subscriptions of the device.

     - Must be instantiated exactly once in every device.

     - Object number must be 4.



    **Properties**:


    .. _ocasubscriptionmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.4"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocasubscriptionmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 4

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocasubscriptionmanager_state:

    .. cpp:member:: OcaSubscriptionManagerState State

        Events enabled or disabled. When events are disabled, (1) Only
        notification from the subscription manager itself are sent to
        subscribers, and (2) the subscription manager saves the object numbers
        of all objects that raise events while notifications are disabled. The
        saved numbers are eventually returned by the **SynchronizeState** event
        that occurs when notifications are re-enabled.

        This property has id ``3.1``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocasubscriptionmanager_addsubscription:

    .. cpp:function:: OcaStatus AddSubscription(OcaEvent Event, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds an EV1 subscription to an event. The subscription is added for the
        session on which the command came in. If a subscription identical to the
        one being requested already exists, an additional one shall not be
        added. Two subscriptions are identical if the **Event, Subscriber,
        NotificationDeliveryMode**, and **DestinationInformation** parameters
        are all identical. **Deprecated** in version 3 of this class, replaced
        by **AddPropertyChangeSubscription(..).** Deprecated in version 3 of
        this class, and replaced by **AddSubscription2**.

        This method has id ``3.1``.

        - :cpp:expr:`Event`: Input parameter.


        - :cpp:expr:`Subscriber`: Input parameter.


        - :cpp:expr:`SubscriberContext`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_removesubscription:

    .. cpp:function:: OcaStatus RemoveSubscription(OcaEvent Event, OcaMethod Subscriber)

        Removes all EV1 subscriptions to the given event with the given
        **OcaMethod**. **Deprecated** in version 3 of this class, and replaced
        by **RemoveSubscription2**.

        This method has id ``3.2``.

        - :cpp:expr:`Event`: Input parameter.


        - :cpp:expr:`Subscriber`: Input parameter.


    .. _ocasubscriptionmanager_disablenotifications:

    .. cpp:function:: OcaStatus DisableNotifications()

        Temporarily disables emitting of event notifications to all subscribers,
        not just to the subscriber calling this method. Events from the
        Subscription Manager itself are not disabled. This method can be used if
        either a controller or the local device knows that it is going to change
        the state of the device significantly, which could lead to a
        notification storm of events. Invoking this method will prevent the
        notification storm. The event '03e01 EventsDisabled' will be raised to
        notify all controllers of the fact that events are temporarily disabled.
        The subscription manager will start collecting the object numbers of the
        objects that raise events, so that it can pass a list of changed objects
        once the events are re-enabled. The return value indicates if disabling
        events succeeded.

        This method has id ``3.3``.

    .. _ocasubscriptionmanager_reenablenotifications:

    .. cpp:function:: OcaStatus ReEnableNotifications()

        Re-enables the sending of event notifications to all subscribers. When
        events are re-enabled, the subscription manager will raise the
        **SynchronizeState** event, passing the list of objects that have
        changed state. Subsequently, the subscription manager will transmit all
        notifications as normal. If the connection to the controller that
        invoked the **DisableEvents()** is lost, this method will be called
        automatically to prevent the situation in which the raising of events
        would never be re-enabled.

        This method has id ``3.4``.

    .. _ocasubscriptionmanager_addpropertychangesubscription:

    .. cpp:function:: OcaStatus AddPropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber, OcaBlob SubscriberContext, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds an EV1 subscription to the **PropertyChanged** event in the object
        **Emitter** for changes of the property **Property**. If a subscription
        identical to the one being requested already exists, an additional one
        shall not be added. Two subscriptions are identical if the **Emitter,
        Property, Subscriber, SubsciberContext, NotificationDeliveryMode,** and
        **DestinationInformation** parameters are all identical. **Deprecated**
        in version 3 of this class, replaced by
        **AddPropertyChangeSubscription2(..).**

        This method has id ``3.5``.

        - :cpp:expr:`Emitter`: Input parameter.


        - :cpp:expr:`Property`: Input parameter.


        - :cpp:expr:`Subscriber`: Input parameter.


        - :cpp:expr:`SubscriberContext`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_removepropertychangesubscription:

    .. cpp:function:: OcaStatus RemovePropertyChangeSubscription(OcaONo Emitter, OcaPropertyID Property, OcaMethod Subscriber)

        Removes any EV1 subscription to a **PropertyChanged** event with the
        given Emitter, Property, Subscriber, SubscriberContext,
        NotificationDeliveryMode, and DestinationInformation. **Deprecated** in
        version 3 of this class, replaced by
        **RemovePropertyChangeSubscription2(...).**

        This method has id ``3.6``.

        - :cpp:expr:`Emitter`: Input parameter.


        - :cpp:expr:`Property`: Input parameter.


        - :cpp:expr:`Subscriber`: Input parameter.


    .. _ocasubscriptionmanager_getmaximumsubscribercontextlength:

    .. cpp:function:: OcaStatus GetMaximumSubscriberContextLength(OcaUint16 &Max)

        Returns maximum byte length of payload of EV1 subscriber context
        parameter that this device supports. This returned value shall be either
        zero or four. If the returned payload length is not zero, it shall be
        four. No other values shall be allowed, and the returned value shall not
        change once the device has initialized. **Deprecated** in version 3 of
        this class. Not used in EV2. NOTE: In AES70-2015, arbitrary subscriber
        context lengths were allowed; this is no longer true.

        This method has id ``3.7``.

        - :cpp:expr:`Max`: Output parameter.


    .. _ocasubscriptionmanager_addsubscription2:

    .. cpp:function:: OcaStatus AddSubscription2(OcaEvent Event, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds an EV2 subscription.

        This method has id ``3.8``.

        - :cpp:expr:`Event`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_removesubscription2:

    .. cpp:function:: OcaStatus RemoveSubscription2(OcaEvent Event, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Removes all EV2 subscriptions with the given **Event**,
        **NotificationDeliveryMode**, and **DestinationInformation**.

        This method has id ``3.9``.

        - :cpp:expr:`Event`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_addpropertychangesubscription2:

    .. cpp:function:: OcaStatus AddPropertyChangeSubscription2(OcaONo Emitter, OcaPropertyID Property, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Adds an EV2 subscription to the **PropertyChanged** event in the object
        **Emitter** for changes of the property **Property**. If a subscription
        identical to the one being requested already exists, an additional one
        shall not be added and the method shall return the status value
        **InvalidRequest**. Two subscriptions are identical if the **Emitter,
        Property, NotificationDeliveryMode,** and **DestinationInformation**
        parameters are all identical.

        This method has id ``3.10``.

        - :cpp:expr:`Emitter`: Input parameter.


        - :cpp:expr:`Property`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_removepropertychangesubscription2:

    .. cpp:function:: OcaStatus RemovePropertyChangeSubscription2(OcaONo Emitter, OcaPropertyID Property, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Removes all EV2 subscriptions to **PropertyChanged** events with the
        given **Emitter**, **Property**, **NotificationDeliveryMode**, and
        **DestinationInformation**.

        This method has id ``3.11``.

        - :cpp:expr:`Emitter`: Input parameter.


        - :cpp:expr:`Property`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_addsubscription2list:

    .. cpp:function:: OcaStatus AddSubscription2List(OcaList<OcaEvent> Events, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation, OcaList<OcaStatus> &ResultStatuses)

        Adds a list of EV2 subscriptions. **OcaStatus** return values from this
        method are as follows:

         - **OK**: Requested subscriptions were attempted; all, none, or some
           succeeded. Individual subscription result details are returned in
           parameter **ResultStatuses**.

         - **<anything else>:** Problem - no subscription attempts were made.



        This method has id ``3.12``.

        - :cpp:expr:`Events`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


        - :cpp:expr:`ResultStatuses`: Output parameter.


    .. _ocasubscriptionmanager_removesubscription2list:

    .. cpp:function:: OcaStatus RemoveSubscription2List(OcaList<OcaEvent> Events, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Removes all EV2 subscriptions in the given list of Events that have the
        specified **NotificationDeliveryMode** and **DestinationInformation**.

        This method has id ``3.13``.

        - :cpp:expr:`Events`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    .. _ocasubscriptionmanager_addpropertychangesubscription2list:

    .. cpp:function:: OcaStatus AddPropertyChangeSubscription2List(OcaList<OcaONo> Emitters, OcaList<OcaPropertyID> Properties, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation, OcaList<OcaStatus> ResultStatuses)

        Adds a list of EV2 property-change subscriptions. **OcaStatus** return
        values from this method are as follows:

         - **OK**: Requested subscriptions were attempted; all, none, or some
           succeeded. Individual subscription result details are returned in
           list parameter **ResultStatuses**.

         - **<anything else>:** Problem - no subscription attempts were made.


        If a subscription identical to the one being requested already exists,
        an additional one shall not be added and the method shall return the
        **ResultStatuses** value **InvalidRequest**. Two subscriptions are
        identical if the **Emitter, Property, NotificationDeliveryMode,** and
        **DestinationInformation** parameters are all identical.

        This method has id ``3.14``.

        - :cpp:expr:`Emitters`: Input parameter.


        - :cpp:expr:`Properties`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


        - :cpp:expr:`ResultStatuses`: Input parameter.


    .. _ocasubscriptionmanager_removepropertychangesubscription2list:

    .. cpp:function:: OcaStatus RemovePropertyChangeSubscription2List(OcaList<OcaONo> Emitters, OcaList<OcaPropertyID> Properties, OcaNotificationDeliveryMode NotificationDeliveryMode, OcaNetworkAddress DestinationInformation)

        Removes all EV2 property-change subscriptions in the given lists of
        Events and Properties that have the specified
        **NotificationDeliveryMode** and **DestinationInformation**.

        This method has id ``3.15``.

        - :cpp:expr:`Emitters`: Input parameter.


        - :cpp:expr:`Properties`: Input parameter.


        - :cpp:expr:`NotificationDeliveryMode`: Input parameter.


        - :cpp:expr:`DestinationInformation`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`


    **Events**:


    .. _ocasubscriptionmanager_notificationsdisabled:

    .. cpp:function:: void NotificationsDisabled()

        Event that is raised when the value of the **State** property changes
        from **Normal **to **EventsDisabled.**

        This event has id ``3.1``.

    .. _ocasubscriptionmanager_synchronizestate:

    .. cpp:function:: void SynchronizeState(OcaObjectListEventData objectsWithUpdatedState)

        Event that is raised when the value of the **State** property changes
        from **EventsDisabled **to **Normal.** Event data includes a lists of
        which objects changed state during the period that notifications were
        disabled.

        This event has id ``3.2``.
