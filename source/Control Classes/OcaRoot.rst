.. _ocaroot:

1  OcaRoot
==========


.. cpp:class:: OcaRoot

    The abstract root class of which all OCA classes derive. It offers
    basic OCA functionality such as locking an object and generalized data
    access.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``1.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``1.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassVersion.

    .. cpp:member:: OcaONo ObjectNumber

        This property has id ``1.3``.

        The object number that uniquely identifies the instantiated object.
        This read-only property must be set at creation of the object. Derived
        objects can hardcode the object number in its constructor, or offer a
        constructor with object number parameter for dynamic allocation of
        object numbers.

    .. cpp:member:: OcaBoolean Lockable

        This property has id ``1.4``.

        Read-only property that indicates whether the object is lockable or
        non-lockable. The property value must be set during construction of
        the object.

    .. cpp:member:: OcaString Role

        This property has id ``1.5``.

        Read-only text property that describes object's role in the device.
        Particularly useful for workers, e.g. "Input 1 Gain".

    .. cpp:function:: OcaStatus GetClassIdentification(OcaClassIdentification &ClassIdentification)

        This method has id ``1.1``.

        Gets the class identification, a structure that contains the ClassID
        and ClassVersion. The return value indicates whether the property was
        successfully retrieved.

        :param OcaClassIdentification ClassIdentification: Output parameter.

    .. cpp:function:: OcaStatus GetLockable(OcaBoolean &lockable)

        This method has id ``1.2``.

        Gets the value of the Lockable property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean lockable: Output parameter.

    .. cpp:function:: OcaStatus LockTotal()

        This method has id ``1.3``.

        Locks the object totally, so that it can only be accessed for reading
        or writing by the lockholder. If the device is read-only locked (by a
        prior call to LockReadonly()) when Lock() is called by the same
        lockholder, the lock state is upgraded to total. If the call is from a
        session other than the lockholder's, the call fails. The return value
        indicates whether the operation succeeded.


    .. cpp:function:: OcaStatus Unlock()

        This method has id ``1.4``.

        Unlocks the object so that it can be freely accessed again. This
        method can only succeed if it is called by the lockholder. The return
        value indicates whether the operation succeeded.


    .. cpp:function:: OcaStatus GetRole(OcaString &Role)

        This method has id ``1.5``.

        Returns value of Role property. The return value indicates whether the
        operation succeeded.

        :param OcaString Role: Output parameter.

    .. cpp:function:: OcaStatus LockReadonly()

        This method has id ``1.6``.

        Locks the object so that its properties may only be modified by the
        lockholder, but others can still retrieve property values. If the
        device is already locked (by a prior call to Lock() or LockReadonly())
        when LockReadonly() is called by the same lockholder, the lock state
        is set to read-only. If the call is from a session other than the
        lockholder's, the call fails. The return value indicates whether the
        operation succeeded.


