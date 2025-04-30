.. _ocadevicetimemanager:

1.3.10  OcaDeviceTimeManager
============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaDeviceTimeManager <ocadevicetimemanager>`

.. cpp:class:: OcaDeviceTimeManager: OcaManager

    Manager that allows controlling and monitoring a device's time-of-day clock,
    and that collects the device's time source objects.

     - Must be instantiated in every device that has more than one time source
       object. In this context, a "time source object" is an instance of
       **OcaTimeSource** or a subclass of it.

     - May be instantiated at most once in any device.

     - If instantiated, object number must be 10.


    Note: The clock value is accessible via Get and Set methods, but has not
    been defined as a public property because its value is volatile and should
    not cause property-change events. The current value of the **OcaTimeSource**
    object designated by the **CurrentDeviceTimeSource** property of this
    Manager is known as the **Device Time**. The property **TimeSources** was
    added in version 2 of this class.

    **Properties**:


    .. _ocadevicetimemanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.10"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadevicetimemanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocadevicetimemanager_currentdevicetimesource:

    .. cpp:member:: OcaONo CurrentDeviceTimeSource

        ONo of the **OcaTimeSource** object that represents current time source
        for this device's device time, or zero if none.

        This property has id ``3.2``.

    .. _ocadevicetimemanager_timesources:

    .. cpp:member:: OcaList<OcaONo> TimeSources

        The list of **ONos** of **OcaTimeSource** objects in this device

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


    .. _ocadevicetimemanager_getdevicetimentp:

    .. cpp:function:: OcaStatus GetDeviceTimeNTP(OcaTimeNTP &DeviceTime)

        Get current value of device time-of-day clock in NTP format.
        **Deprecated** in version 3 of this class.

        This method has id ``3.1``.

        - :cpp:expr:`DeviceTime`: Output parameter.


    .. _ocadevicetimemanager_setdevicetimentp:

    .. cpp:function:: OcaStatus SetDeviceTimeNTP(OcaTimeNTP DeviceTime)

        Sets device time-of-day clock in NTP format. Not available if a time
        source is identified in property CurrentDeviceTimeSource. **Deprecated**
        in version 3 of this class.

        This method has id ``3.2``.

        - :cpp:expr:`DeviceTime`: Input parameter.


    .. _ocadevicetimemanager_gettimesources:

    .. cpp:function:: OcaStatus GetTimeSources(OcaList<OcaONo> &TimeSourceONos)

        Gets the list of object numbers of OcaTimeSource instances in this
        device.

        This method has id ``3.3``.

        - :cpp:expr:`TimeSourceONos`: Output parameter.


    .. _ocadevicetimemanager_getcurrentdevicetimesource:

    .. cpp:function:: OcaStatus GetCurrentDeviceTimeSource(OcaONo &TimeSourceONo)

        Retrieves **ONo** of current time source object, or zero if none.

        This method has id ``3.4``.

        - :cpp:expr:`TimeSourceONo`: Output parameter.


    .. _ocadevicetimemanager_setcurrentdevicetimesource:

    .. cpp:function:: OcaStatus SetCurrentDeviceTimeSource(OcaONo TimeSourceONo)

        Sets **ONo** of current time source object, or zero if none.

        This method has id ``3.5``.

        - :cpp:expr:`TimeSourceONo`: Input parameter.


    .. _ocadevicetimemanager_getdevicetime:

    .. cpp:function:: OcaStatus GetDeviceTime(OcaTime &DeviceTime)

        Get current value of device time-of-day clock.

        This method has id ``3.6``.

        - :cpp:expr:`DeviceTime`: Output parameter.


    .. _ocadevicetimemanager_setdevicetime:

    .. cpp:function:: OcaStatus SetDeviceTime(OcaTime DeviceTime)

        Sets device time-of-day clock Not available if a time source is
        identified in property **CurrentDeviceTimeSource**.

        This method has id ``3.7``.

        - :cpp:expr:`DeviceTime`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

