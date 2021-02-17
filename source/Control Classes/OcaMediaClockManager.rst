.. _ocamediaclockmanager:

1.3.7  OcaMediaClockManager
===========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaMediaClockManager <ocamediaclockmanager>` 

.. cpp:class:: OcaMediaClockManager: OcaManager

    Optional manager that collects all media clocks the device uses.
    
    - Must be instantiated once for every device that has more than one
    media clock object. In this context, "media clock" means an instance
    of **OcaMediaClock** , **OcaMediaClock3** , or any subclass of these
    classes.
    
    
    - If instantiated, object number must be 7.
    

    **Properties**:

    .. _ocamediaclockmanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocamediaclockmanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocamediaclockmanager_clocksourcetypessupported:

    .. cpp:member:: OcaList<OcaMediaClockType> ClockSourceTypesSupported

        List of clock source types supported by **OcaMediaClock** objects in
        this device. Note: In AES70-2017, this method is deprecated. It only
        reflects the clock types of **OcaMediaClock** objects, which are now
        deprecated. It does not apply to **OcaMediaClock3** objects, since
        these do not have type attributes. If the number of **OcaMediaClock**
        objects in the device is zero, this property is empty.

        This property has id ``3.1``.

    .. _ocamediaclockmanager_clocks:

    .. cpp:member:: OcaList<OcaONo> Clocks

        Object numbers of **OcaMediaClock** objects, one for each clock which
        this device uses and/or sources. Note: In AES70-2017, this property is
        deprecated.

        This property has id ``3.2``.

    .. _ocamediaclockmanager_clock3s:

    .. cpp:member:: OcaList<OcaONo> Clock3s

        Object numbers of **OcaMediaClock3** objects, one for each clock which
        this device uses and/or sources.

        This property has id ``3.3``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocamediaclockmanager_getclocks:

    .. cpp:function:: OcaStatus GetClocks(OcaList<OcaONo> &Clocks)

        Gets the list of object numbers of **OcaMediaClock** instances in this
        device. Return value indicates whether list was successfully
        retrieved. Note: In AES70-2017, this method is deprecated.

        This method has id ``3.1``.

        :param OcaList<OcaONo> Clocks: Output parameter.

    .. _ocamediaclockmanager_getmediaclocktypessupported:

    .. cpp:function:: OcaStatus GetMediaClockTypesSupported(OcaList<OcaMediaClockType> &MediaClockTypes)

        Gets the list of media clock types supported by **OcaMediaClock**
        objects in the device. Return value indicates whether the list was
        successfully retrieved. Note : In AES70-2017, this method is
        deprecated.

        This method has id ``3.2``.

        :param OcaList<OcaMediaClockType> MediaClockTypes: Output parameter.

    .. _ocamediaclockmanager_getclock3s:

    .. cpp:function:: OcaStatus GetClock3s(OcaList<OcaONo> &Clocks)

        Gets the list of object numbers of **OcaMediaClock3** instances in
        this device. Return value indicates whether list was successfully
        retrieved.

        This method has id ``3.3``.

        :param OcaList<OcaONo> Clocks: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
