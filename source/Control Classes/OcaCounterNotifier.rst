.. _ocacounternotifier:

1.2.18  OcaCounterNotifier
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaCounterNotifier <ocacounternotifier>`

.. cpp:class:: OcaCounterNotifier: OcaAgent

    **Notifier** for an OCA counter. Observes the value of the counter and emits
    a **CounterUpdate** notification when specified criteria are met. An OCA
    counter wishing to notify controllers of its changing value can designate
    one or more notifier objects to which the controllers may subscribe. See the
    definition of the **OcaCounter** datatype for additional detail.
    Notification criteria are as follows:

     - **Threshold**. The counter value meets a certain comparison condition. A
       selection of comparison operators is available. The **Operator** property
       is the comparison operator to use for **Threshold.**

     - **Period**. The value of the** Period** parameter, if nonzero, is a the
       time interval for the recurrent timed emission of **CounterUpdate**
       events. Such events are emitted regardless of the counter's value.

     - **CountIncrement.** An **CounterUpdate** event is emitted every time the
       counter value changes by an amount equal to or greater than the value of
       this parameter.


    ** **For combinations of (1), (2), and (3), the criteria are applied as
    follows: if (1) is specified and not satisfied, then no observation is
    emitted. else if (2) is specified and satisfied or (3) is specified and
    satisfied, then an observation is emitted. end end Regardless of filter
    parameter values, a notification is always emitted when a counter is
    explicitly reset using a **Reset()** method. An **OcaCounterNotifier**
    instance and the counter it observes are bound at the time the
    **OcaCounterNotifier** instance is constructed. For static devices,
    construction will occur during manufacture, or possibly during a subsequent
    hardware configuration step. For reconfigurable devices, construction might
    be done by online controllers as part of device configuration activity.

    **Properties**:


    .. _ocacounternotifier_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.18"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocacounternotifier_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocacounternotifier_filterparameters:

    .. cpp:member:: OcaCounterNotifierFilterParameters FilterParameters

        Conditions for emission of the **Observation** event

        This property has id ``3.1``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocacounternotifier_getlastupdate:

    .. cpp:function:: OcaStatus GetLastUpdate(OcaList<OcaCounterUpdate> &Notifications)

        Returns the payload of the most recent **CounterUpdate** event emitted
        by this object.

        This method has id ``3.1``.

        - :cpp:expr:`Notifications`: Output parameter.


    .. _ocacounternotifier_getfilterparameters:

    .. cpp:function:: OcaStatus GetFilterParameters(OcaCounterNotifierFilterParameters &Parameters)

        Returns this notifier's set of filter parameters.

        This method has id ``3.2``.

        - :cpp:expr:`Parameters`: Output parameter.


    .. _ocacounternotifier_setfilterparameters:

    .. cpp:function:: OcaStatus SetFilterParameters(OcaCounterNotifierFilterParameters Parameters)

        Sets this notifier's set of filter parameters.

        This method has id ``3.3``.

        - :cpp:expr:`Parameters`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaAgent::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`


    **Events**:


    .. _ocacounternotifier_counterupdate:

    .. cpp:function:: void CounterUpdate(OcaCounterUpdateEventData eventData)

        Event raised when filter conditions are met.

        This event has id ``3.1``.
