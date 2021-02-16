.. _ocadevicetimemanager:

1.3.10  OcaDeviceTimeManager
============================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaDeviceTimeManager: OcaManager

    Manager that allows controlling and monitoring a device's time-of-day
    clock, and that collects the device's time source objects.
    
    - Must be instantiated once in every device that has more than one
    time source object. In this context, a "time source object" is an
    instance of **OcaTimeSource** or a subclass of it.
    
    
    - If instantiated, object number must be 10.
    Note: The clock value is accessible via Get and Set methods, but has
    not been defined as a public property because its value is volatile
    and should not cause property-change events. The current value of the
    **OcaTimeSource** object designated by the **CurrentDeviceTimeSource**
    property of this Manager is known as the **Device Time** . The
    property **TimeSources** was added in version 2 of this class.

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

    .. cpp:member:: OcaList<OcaONo> TimeSources

        This property has id ``3.1``.

        The list of ONos of OcaTimeSource objects in this device

    .. cpp:member:: OcaONo CurrentDeviceTimeSource

        This property has id ``3.2``.

        The current time source for this device's device time, or zero if
        none.

    .. cpp:member:: OcaTimePTP DeviceTimePTP

        This property has id ``3.0``.

        The current device time. Defined as a private property so that clock
        updates don't generate property-change events.

    .. cpp:function:: OcaStatus GetDeviceTimeNTP(OcaTimeNTP &DeviceTime)

        This method has id ``3.1``.

        Get current value of device time-of-day clock in NTP format. Return
        value indicates whether value was successfully retrieved. This method
        is _optional_ and _deprecated_ .

        :param OcaTimeNTP DeviceTime: Output parameter.

    .. cpp:function:: OcaStatus SetDeviceTimeNTP(OcaTimeNTP DeviceTime)

        This method has id ``3.2``.

        Sets device time-of-day clock in NTP format. Return value indicates
        whether value was successfully set. Not available if a time source is
        identified in property CurrentDeviceTimeSource. This method is
        _optional_ and _deprecated_ .

        :param OcaTimeNTP DeviceTime: Input parameter.

    .. cpp:function:: OcaStatus GetTimeSources(OcaList<OcaONo> &TimeSourceONos)

        This method has id ``3.3``.

        Returns list of object numbers of OcaTimeSource instances in this
        device. Return value indicates whether list was successfully
        retrieved.

        :param OcaList<OcaONo> TimeSourceONos: Output parameter.

    .. cpp:function:: OcaStatus GetCurrentDeviceTimeSource(OcaONo &TimeSourceONo)

        This method has id ``3.4``.

        Retrieves ONo of current time source object, or zero if none. Return
        value indicates whether value was successfully retrieved.

        :param OcaONo TimeSourceONo: Output parameter.

    .. cpp:function:: OcaStatus SetCurrentDeviceTimeSource(OcaONo TimeSourceONo)

        This method has id ``3.5``.

        Sets ONo of current time source object, or zero if none. Return value
        indicates whether value was successfully retrieved.

        :param OcaONo TimeSourceONo: Input parameter.

    .. cpp:function:: OcaStatus GetDeviceTimePTP(OcaTimePTP &DeviceTime)

        This method has id ``3.6``.

        Get current value of device time-of-day clock in PTP format. Return
        value indicates whether value was successfully retrieved.

        :param OcaTimePTP DeviceTime: Output parameter.

    .. cpp:function:: OcaStatus SetDeviceTimePTP(OcaTimePTP DeviceTime)

        This method has id ``3.7``.

        Sets device time-of-day clock in PTP format. Return value indicates
        whether value was successfully set. Not available if a time source is
        identified in property CurrentDeviceTimeSource.

        :param OcaTimePTP DeviceTime: Input parameter.

