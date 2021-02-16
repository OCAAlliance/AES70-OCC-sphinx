.. _ocamediaclockmanager:

1.3.7  OcaMediaClockManager
===========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaMediaClockManager: OcaManager

    Optional manager that collects all media clocks the device uses.
    
    - Must be instantiated once for every device that has more than one
    media clock object. In this context, "media clock" means an instance
    of **OcaMediaClock** , **OcaMediaClock3** , or any subclass of these
    classes.
    
    
    - If instantiated, object number must be 7.
    

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaList<OcaMediaClockType> ClockSourceTypesSupported

        This property has id ``3.1``.

        List of clock source types supported by **OcaMediaClock** objects in
        this device. Note: In AES70-2017, this method is deprecated. It only
        reflects the clock types of **OcaMediaClock** objects, which are now
        deprecated. It does not apply to **OcaMediaClock3** objects, since
        these do not have type attributes. If the number of **OcaMediaClock**
        objects in the device is zero, this property is empty.

    .. cpp:member:: OcaList<OcaONo> Clocks

        This property has id ``3.2``.

        Object numbers of **OcaMediaClock** objects, one for each clock which
        this device uses and/or sources. Note: In AES70-2017, this property is
        deprecated.

    .. cpp:member:: OcaList<OcaONo> Clock3s

        This property has id ``3.3``.

        Object numbers of **OcaMediaClock3** objects, one for each clock which
        this device uses and/or sources.

    .. cpp:function:: OcaStatus GetClocks(OcaList<OcaONo> &Clocks)

        This method has id ``3.1``.

        Gets the list of object numbers of **OcaMediaClock** instances in this
        device. Return value indicates whether list was successfully
        retrieved. Note: In AES70-2017, this method is deprecated.

        :param OcaList<OcaONo> Clocks: Output parameter.

    .. cpp:function:: OcaStatus GetMediaClockTypesSupported(OcaList<OcaMediaClockType> &MediaClockTypes)

        This method has id ``3.2``.

        Gets the list of media clock types supported by **OcaMediaClock**
        objects in the device. Return value indicates whether the list was
        successfully retrieved. Note : In AES70-2017, this method is
        deprecated.

        :param OcaList<OcaMediaClockType> MediaClockTypes: Output parameter.

    .. cpp:function:: OcaStatus GetClock3s(OcaList<OcaONo> &Clocks)

        This method has id ``3.3``.

        Gets the list of object numbers of **OcaMediaClock3** instances in
        this device. Return value indicates whether list was successfully
        retrieved.

        :param OcaList<OcaONo> Clocks: Output parameter.

