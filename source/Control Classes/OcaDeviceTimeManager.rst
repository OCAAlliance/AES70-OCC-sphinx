.. _ocadevicetimemanager:

1.3.10  OcaDeviceTimeManager
============================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaDeviceTimeManager <ocadevicetimemanager>` 

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

    **Properties**:

    .. _ocadevicetimemanager_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocadevicetimemanager_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocadevicetimemanager_timesources:

    .. cpp:member:: OcaList<OcaONo> TimeSources

        The list of ONos of OcaTimeSource objects in this device

        This property has id ``3.1``.

    .. _ocadevicetimemanager_currentdevicetimesource:

    .. cpp:member:: OcaONo CurrentDeviceTimeSource

        The current time source for this device's device time, or zero if
        none.

        This property has id ``3.2``.

    .. _ocadevicetimemanager_devicetimeptp:

    .. cpp:member:: OcaTimePTP DeviceTimePTP

        The current device time. Defined as a private property so that clock
        updates don't generate property-change events.

        This property has id ``3.0``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocadevicetimemanager_getdevicetimentp:

    .. cpp:function:: OcaStatus GetDeviceTimeNTP(OcaTimeNTP &DeviceTime)

        Get current value of device time-of-day clock in NTP format. Return
        value indicates whether value was successfully retrieved. This method
        is _optional_ and _deprecated_ .

        This method has id ``3.1``.

        :param OcaTimeNTP DeviceTime: Output parameter.

    .. _ocadevicetimemanager_setdevicetimentp:

    .. cpp:function:: OcaStatus SetDeviceTimeNTP(OcaTimeNTP DeviceTime)

        Sets device time-of-day clock in NTP format. Return value indicates
        whether value was successfully set. Not available if a time source is
        identified in property CurrentDeviceTimeSource. This method is
        _optional_ and _deprecated_ .

        This method has id ``3.2``.

        :param OcaTimeNTP DeviceTime: Input parameter.

    .. _ocadevicetimemanager_gettimesources:

    .. cpp:function:: OcaStatus GetTimeSources(OcaList<OcaONo> &TimeSourceONos)

        Returns list of object numbers of OcaTimeSource instances in this
        device. Return value indicates whether list was successfully
        retrieved.

        This method has id ``3.3``.

        :param OcaList<OcaONo> TimeSourceONos: Output parameter.

    .. _ocadevicetimemanager_getcurrentdevicetimesource:

    .. cpp:function:: OcaStatus GetCurrentDeviceTimeSource(OcaONo &TimeSourceONo)

        Retrieves ONo of current time source object, or zero if none. Return
        value indicates whether value was successfully retrieved.

        This method has id ``3.4``.

        :param OcaONo TimeSourceONo: Output parameter.

    .. _ocadevicetimemanager_setcurrentdevicetimesource:

    .. cpp:function:: OcaStatus SetCurrentDeviceTimeSource(OcaONo TimeSourceONo)

        Sets ONo of current time source object, or zero if none. Return value
        indicates whether value was successfully retrieved.

        This method has id ``3.5``.

        :param OcaONo TimeSourceONo: Input parameter.

    .. _ocadevicetimemanager_getdevicetimeptp:

    .. cpp:function:: OcaStatus GetDeviceTimePTP(OcaTimePTP &DeviceTime)

        Get current value of device time-of-day clock in PTP format. Return
        value indicates whether value was successfully retrieved.

        This method has id ``3.6``.

        :param OcaTimePTP DeviceTime: Output parameter.

    .. _ocadevicetimemanager_setdevicetimeptp:

    .. cpp:function:: OcaStatus SetDeviceTimePTP(OcaTimePTP DeviceTime)

        Sets device time-of-day clock in PTP format. Return value indicates
        whether value was successfully set. Not available if a time source is
        identified in property CurrentDeviceTimeSource.

        This method has id ``3.7``.

        :param OcaTimePTP DeviceTime: Input parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    
