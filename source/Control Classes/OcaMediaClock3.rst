.. _ocamediaclock3:

1.2.15  OcaMediaClock3
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaMediaClock3 <ocamediaclock3>`

.. cpp:class:: OcaMediaClock3: OcaAgent

    A media clock, internal or external. OCA Connection Management 3 (OCA-CM3)
    version.

    **Properties**:


    .. _ocamediaclock3_availability:

    .. cpp:member:: OcaMediaClockAvailability Availability

        Availability of the media clock.

        This property has id ``3.1``.

    .. _ocamediaclock3_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.15"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediaclock3_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamediaclock3_currentrate:

    .. cpp:member:: OcaMediaClockRate CurrentRate

        Current clock rate

        This property has id ``3.4``.

    .. _ocamediaclock3_offset:

    .. cpp:member:: OcaTime Offset

        Offset of media clock time from reference time. Note: For RTP-based
        media transport networks, this value is NOT the RTP time offset. RTP
        time offset is an implementation detail that is out of AES70's scope.

        This property has id ``3.3``.

    .. _ocamediaclock3_supportedrates:

    .. cpp:member:: OcaMap<OcaONo, OcaList<OcaMediaClockRate>> SupportedRates

        Map of supported rates for each supported time source. Key of map is
        **ONo** of an **OcaTimeSource** object; value is list of supported clock
        rates for the given time source.

        This property has id ``3.5``.

    .. _ocamediaclock3_timesourceono:

    .. cpp:member:: OcaONo TimeSourceONo

        **ONo** of time source object that drives this media clock.

        This property has id ``3.2``.

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


    .. _ocamediaclock3_getavailability:

    .. cpp:function:: OcaStatus GetAvailability(OcaMediaClockAvailability &Availability)

        Gets the value of the **Availability** property.

        This method has id ``3.1``.

        - :cpp:expr:`Availability`: Output parameter.


    .. _ocamediaclock3_setavailability:

    .. cpp:function:: OcaStatus SetAvailability(OcaMediaClockAvailability Availability)

        Sets the value of the **Availability** property. Optional method, need
        not be supported in all implementations.

        This method has id ``3.2``.

        - :cpp:expr:`Availability`: Input parameter.


    .. _ocamediaclock3_getcurrentrate:

    .. cpp:function:: OcaStatus GetCurrentRate(OcaMediaClockRate &Rate, OcaONo &TimeSourceONo)

        Gets the current clock rate and the ONo of the associated
        **OcaTimeSource** object.

        This method has id ``3.3``.

        - :cpp:expr:`Rate`: Output parameter.


        - :cpp:expr:`TimeSourceONo`: Output parameter.


    .. _ocamediaclock3_setcurrentrate:

    .. cpp:function:: OcaStatus SetCurrentRate(OcaMediaClockRate Rate, OcaONo TimeSourceONo)

        Sets the clock rate and the ONo of the associated **OcaTimeSource**
        object. Optional method, may not be supported in all implementations.

        This method has id ``3.4``.

        - :cpp:expr:`Rate`: Input parameter.


        - :cpp:expr:`TimeSourceONo`: Input parameter.


    .. _ocamediaclock3_getoffset:

    .. cpp:function:: OcaStatus GetOffset(OcaTime &Offset)

        Gets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object.

        This method has id ``3.5``.

        - :cpp:expr:`Offset`: Output parameter.


    .. _ocamediaclock3_setoffset:

    .. cpp:function:: OcaStatus SetOffset(OcaTime Offset)

        Sets the offset of this media clock's time from that of the associated
        **OcaTimeSource** object. Optional method, may not be supported in all
        implementations.

        This method has id ``3.6``.

        - :cpp:expr:`Offset`: Input parameter.


    .. _ocamediaclock3_getsupportedrates:

    .. cpp:function:: OcaStatus GetSupportedRates(OcaMap<OcaONo, OcaList<OcaMediaClockRate>> &Rates)

        Gets the list of supported media clock rates for each supported time
        source.

        This method has id ``3.7``.

        - :cpp:expr:`Rates`: Output parameter.


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

