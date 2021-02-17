.. _ocamediaclock3:

1.2.15  OcaMediaClock3
======================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaMediaClock3 <ocamediaclock3>` 

.. cpp:class:: OcaMediaClock3: OcaAgent

    A media clock, internal or external. OCA Connection Management 3
    (OCA-CM3) version.

    **Properties**:

    .. _ocamediaclock3_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocamediaclock3_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocamediaclock3_availability:

    .. cpp:member:: OcaMediaClockAvailability Availability

        Availability of media clock.

        This property has id ``3.1``.

    .. _ocamediaclock3_timesourceono:

    .. cpp:member:: OcaONo TimeSourceONo

        ONo of time source that drives this media clock.

        This property has id ``3.2``.

    .. _ocamediaclock3_offset:

    .. cpp:member:: OcaTimePTP Offset

        Offset of media clock time from reference time. Note: For RTP-based
        media transport networks, this value is NOT the RTP time offset. RTP
        time offset is an implementation detail that is out of AES70's scope.

        This property has id ``3.3``.

    .. _ocamediaclock3_currentrate:

    .. cpp:member:: OcaMediaClockRate CurrentRate

        Current clock rate

        This property has id ``3.4``.

    .. _ocamediaclock3_supportedrates:

    .. cpp:member:: OcaMap<OcaONo, OcaList> SupportedRates

        Map of supported rates for each supported time source. Key of map is
        ONo of supported time source; value is list of supported clock rates
        for the given time source. Private parameter, does not generate
        property-change events.

        This property has id ``3.5``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocamediaclock3_getavailability:

    .. cpp:function:: OcaStatus GetAvailability(OcaMediaClockAvailability &Availability)

        Gets the value of the **Availability** property. The return value
        indicates whether the value was successfully retrieved.

        This method has id ``3.1``.

        :param OcaMediaClockAvailability Availability: Output parameter.

    .. _ocamediaclock3_setavailability:

    .. cpp:function:: OcaStatus SetAvailability(OcaMediaClockAvailability Availability)

        Sets the value of the **Availability** property. The return value
        indicates whether the value was successfully set. Optional method, may
        not be supported in all implementations.

        This method has id ``3.2``.

        :param OcaMediaClockAvailability Availability: Input parameter.

    .. _ocamediaclock3_getcurrentrate:

    .. cpp:function:: OcaStatus GetCurrentRate(OcaMediaClockRate &Rate, OcaONo &TimeSourceONo)

        Gets the current clock rate and the ONo of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully retrieved.

        This method has id ``3.3``.

        :param OcaMediaClockRate Rate: Output parameter.
        :param OcaONo TimeSourceONo: Output parameter.

    .. _ocamediaclock3_setcurrentrate:

    .. cpp:function:: OcaStatus SetCurrentRate(OcaMediaClockRate Rate, OcaONo TimeSourceONo)

        Sets the clock rate and the ONo of the associated **OcaTimeSource**
        object. The return value indicates whether the value was successfully
        set. Optional method, may not be supported in all implementations.

        This method has id ``3.4``.

        :param OcaMediaClockRate Rate: Input parameter.
        :param OcaONo TimeSourceONo: Input parameter.

    .. _ocamediaclock3_getoffset:

    .. cpp:function:: OcaStatus GetOffset(OcaTimePTP &Offset)

        Gets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully retrieved.

        This method has id ``3.5``.

        :param OcaTimePTP Offset: Output parameter.

    .. _ocamediaclock3_setoffset:

    .. cpp:function:: OcaStatus SetOffset(OcaTimePTP Offset)

        Sets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object. The return value indicates whether the value
        was successfully set. Optional method, may not be supported in all
        implementations.

        This method has id ``3.6``.

        :param OcaTimePTP Offset: Input parameter.

    .. _ocamediaclock3_getsupportedrates:

    .. cpp:function:: OcaStatus GetSupportedRates(OcaMap<OcaONo, OcaList> &Rates)

        Gets the list of supported media clock rates for the given time
        source. The return value indicates whether the list was successfully
        retrieved.

        This method has id ``3.7``.

        :param OcaMap<OcaONo, OcaList> Rates: Output parameter.


    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


