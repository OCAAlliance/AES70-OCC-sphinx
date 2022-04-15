.. _ocaroot:

1  OcaRoot
==========

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` 

.. cpp:class:: OcaRoot

    The abstract root class of which all OCA classes derive. It offers basic OCA functionality such as locking an object and generalized data access.

    **Properties**:

    .. _ocaroot_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This is a class property instead of an object property. This property will be overridden by each descendant class, in order to specify that class's ClassID.

        This property has id ``1.1``.

    .. _ocaroot_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property will be overridden by each descendant class, in order to specify that class's ClassVersion.

        This property has id ``1.2``.

    .. _ocaroot_objectnumber:

    .. cpp:member:: OcaONo ObjectNumber

        The object number that uniquely identifies the instantiated object. This read-only property must be set at creation of the object. Derived objects can hardcode the object number in its constructor, or offer a constructor with object number parameter for dynamic allocation of object numbers.

        This property has id ``1.3``.

    .. _ocaroot_lockable:

    .. cpp:member:: OcaBoolean Lockable

        Read-only property that indicates whether the object is lockable or non-lockable. The property value must be set during construction of the object.

        This property has id ``1.4``.

    .. _ocaroot_role:

    .. cpp:member:: OcaString Role

        Read-only text property that describes object's role in the device. Particularly useful for workers, e.g. "Input 1 Gain".

        This property has id ``1.5``.


    **Methods**:

    .. _ocaroot_getclassidentification:

    .. cpp:function:: OcaStatus GetClassIdentification(OcaClassIdentification &ClassIdentification)

        Gets the class identification, a structure that contains the ClassID and ClassVersion. The return value indicates whether the property was successfully retrieved.

        This method has id ``1.1``.

        :param OcaClassIdentification ClassIdentification: Output parameter.

    .. _ocaroot_getlockable:

    .. cpp:function:: OcaStatus GetLockable(OcaBoolean &lockable)

        Gets the value of the Lockable property. The return value indicates whether the property was successfully retrieved.

        This method has id ``1.2``.

        :param OcaBoolean lockable: Output parameter.

    .. _ocaroot_locktotal:

    .. cpp:function:: OcaStatus LockTotal()

        Locks the object totally, so that it can only be accessed for reading or writing by the lockholder. If the device is read-only locked (by a prior call to LockReadonly()) when Lock() is called by the same lockholder, the lock state is upgraded to total. If the call is from a session other than the lockholder's, the call fails. The return value indicates whether the operation succeeded.

        This method has id ``1.3``.


    .. _ocaroot_unlock:

    .. cpp:function:: OcaStatus Unlock()

        Unlocks the object so that it can be freely accessed again. This method can only succeed if it is called by the lockholder. The return value indicates whether the operation succeeded.

        This method has id ``1.4``.


    .. _ocaroot_getrole:

    .. cpp:function:: OcaStatus GetRole(OcaString &Role)

        Returns value of Role property. The return value indicates whether the operation succeeded.

        This method has id ``1.5``.

        :param OcaString Role: Output parameter.

    .. _ocaroot_lockreadonly:

    .. cpp:function:: OcaStatus LockReadonly()

        Locks the object so that its properties may only be modified by the lockholder, but others can still retrieve property values. If the device is already locked (by a prior call to Lock() or LockReadonly()) when LockReadonly() is called by the same lockholder, the lock state is set to read-only. If the call is from a session other than the lockholder's, the call fails. The return value indicates whether the operation succeeded.

        This method has id ``1.6``.





    **Events**:

    .. _ocaroot_propertychanged:

    .. cpp:function:: void PropertyChanged(OcaPropertyChangedEventData eventData)

        General event that is emitted when a property changes. In each setter method (of derived classes) this event must be raised with the proper derived event data structure.


