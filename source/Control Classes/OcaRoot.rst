.. _ocaroot:

1  OcaRoot
==========

Class Hierarchy:

:ref:`OcaRoot <ocaroot>`

.. cpp:class:: OcaRoot

    The abstract root class of which all OCA classes derive. It offers basic OCA
    functionality such as locking an object and generalized data access.

    **Properties**:


    .. _ocaroot_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

        This property has id ``1.1``.

    .. _ocaroot_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassVersion.

        This property has id ``1.2``.

    .. _ocaroot_lockable:

    .. cpp:member:: const OcaBoolean Lockable

        Read-only property that indicates whether the object is lockable or
        non-lockable. The property value shall be set during construction of the
        object.

        This property has id ``1.4``.

    .. _ocaroot_lockstate:

    .. cpp:member:: OcaLockState LockState

        Current lock state - none, noWrite, or noReadWrite

        This property has id ``1.6``.

    .. _ocaroot_objectnumber:

    .. cpp:member:: const OcaONo ObjectNumber

        The object number that uniquely identifies the instantiated object. This
        read-only property shall be set at creation of the object. Derived
        objects can hardcode the object number in its constructor, or offer a
        constructor with object number parameter for dynamic allocation of
        object numbers.

        This property has id ``1.3``.

    .. _ocaroot_role:

    .. cpp:member:: const OcaString Role

        Read-only text property that describes object's role in the device.
        Particularly useful for workers, e.g. "Input 1 Gain". Value shall not
        change during the life of the object. Values beginning with "oca" in any
        character case are reserved for AES use.

        This property has id ``1.5``.

    **Methods**:


    .. _ocaroot_getclassidentification:

    .. cpp:function:: OcaStatus GetClassIdentification(OcaClassIdentification &ClassIdentification)

        Gets the class identification, a structure contains the ClassID and
        ClassVersion.

        This method has id ``1.1``.

        - :cpp:expr:`ClassIdentification`: Output parameter.


    .. _ocaroot_getlockable:

    .. cpp:function:: OcaStatus GetLockable(OcaBoolean &lockable)

        Gets the value of the Lockable property.

        This method has id ``1.2``.

        - :cpp:expr:`lockable`: Output parameter.


    .. _ocaroot_setlocknoreadwrite:

    .. cpp:function:: OcaStatus SetLockNoReadWrite()

        Locks the object totally, so that it can only be accessed for reading or
        writing by the lockholder.

         - If the object's **LockState** is **LockNoWrite** by the same
           lockholder, the lock state is upgraded to LockNoReadWrite.

         - If the call is from a session other than the lockholder's, the call
           fails.



        This method has id ``1.3``.

    .. _ocaroot_unlock:

    .. cpp:function:: OcaStatus Unlock()

        Unlocks the object so that it can be freely accessed again. This method
        can only succeed if it is called by the lockholder.

        This method has id ``1.4``.

    .. _ocaroot_getrole:

    .. cpp:function:: OcaStatus GetRole(OcaString &Role)

        Returns value of Role property.

        This method has id ``1.5``.

        - :cpp:expr:`Role`: Output parameter.


    .. _ocaroot_setlocknowrite:

    .. cpp:function:: OcaStatus SetLockNoWrite()

        Locks the object so that it may only be controlled by the lockholder,
        but others can still retrieve property values. If **LockState** is
        **LockNoReadWrite** by the same lockholder, the lock state is downgraded
        to **LockNoWrite**. If the call is from a session other than the
        lockholder's, the call fails.

        This method has id ``1.6``.

    .. _ocaroot_getlockstate:

    .. cpp:function:: OcaStatus GetLockState(OcaLockState &State)

        Returns the current value of the **LockState** property.

        This method has id ``1.7``.

        - :cpp:expr:`State`: Output parameter.


    **Events**:


    .. _ocaroot_propertychanged:

    .. cpp:function:: void PropertyChanged(OcaPropertyChangedEventData eventData)

        General event that is emitted when a property changes. In each setter
        method (of derived classes) this event shall be raised with the proper
        derived event data structure.

        This event has id ``1.1``.
