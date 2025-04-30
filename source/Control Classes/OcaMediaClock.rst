.. _ocamediaclock:

1.2.6  OcaMediaClock
====================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaMediaClock <ocamediaclock>`

.. cpp:class:: OcaMediaClock: OcaAgent

    **DEPRECATED CLASS** *Replaced by* **OcaMediaClock3** A media clock,
    internal or external.

    **Properties**:


    .. _ocamediaclock_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.6"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediaclock_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3


        This property has id ``1.2``.

    .. _ocamediaclock_currentrate:

    .. cpp:member:: OcaMediaClockRate CurrentRate

        Current clock rate

        This property has id ``3.4``.

    .. _ocamediaclock_domainid:

    .. cpp:member:: OcaUint16 DomainID

        Clock domain ID. Arbitrary value.

        This property has id ``3.2``.

    .. _ocamediaclock_lockstate:

    .. cpp:member:: OcaMediaClockLockState LockState

        Lock state of clock.

        This property has id ``3.5``.

    .. _ocamediaclock_ratessupported:

    .. cpp:member:: OcaList<OcaMediaClockRate> RatesSupported

        List of supported rates

        This property has id ``3.3``.

    .. _ocamediaclock_type:

    .. cpp:member:: OcaMediaClockType Type

        Type of clock.

        This property has id ``3.1``.

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


    .. _ocamediaclock_gettype:

    .. cpp:function:: OcaStatus GetType(OcaMediaClockType &Type)

        Gets the value of the **Type** property. The return value indicates
        whether the value was successfully retrieved.

        This method has id ``3.1``.

        - :cpp:expr:`Type`: Output parameter.


    .. _ocamediaclock_settype:

    .. cpp:function:: OcaStatus SetType(OcaMediaClockType Type)

        Sets the value of the **Type** property. The return value indicates
        whether the value was successfully set. Optional method, may not be
        supported in all implementations.

        This method has id ``3.2``.

        - :cpp:expr:`Type`: Input parameter.


    .. _ocamediaclock_getdomainid:

    .. cpp:function:: OcaStatus GetDomainID(OcaUint16 &ID)

        Gets the value of the **DomainID** property. The return value indicates
        whether the value was successfully retrieved.

        This method has id ``3.3``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocamediaclock_setdomainid:

    .. cpp:function:: OcaStatus SetDomainID(OcaUint16 ID)

        Sets the value of the **DomainID** property. The return value indicates
        whether the value was successfully set. Optional method, may not be
        supported in all implementations.

        This method has id ``3.4``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediaclock_getsupportedrates:

    .. cpp:function:: OcaStatus GetSupportedRates(OcaList<OcaMediaClockRate> &ID)

        Gets the list of supported sampling rates. The return value indicates
        whether the list was successfully retrieved.

        This method has id ``3.5``.

        - :cpp:expr:`ID`: Output parameter.


    .. _ocamediaclock_getrate:

    .. cpp:function:: OcaStatus GetRate(OcaMediaClockRate &rate)

        Gets the current sampling rate. The return value indicates whether the
        value was successfully retrieved.

        This method has id ``3.6``.

        - :cpp:expr:`rate`: Output parameter.


    .. _ocamediaclock_setrate:

    .. cpp:function:: OcaStatus SetRate(OcaMediaClockRate rate)

        Sets the sampling rate. The return value indicates whether the rate was
        successfully set.

        This method has id ``3.7``.

        - :cpp:expr:`rate`: Input parameter.


    .. _ocamediaclock_getlockstate:

    .. cpp:function:: OcaStatus GetLockState(OcaMediaClockLockState &state)

        Gets the current media clock lock state. The return value indicates
        whether the value was successfully retrieved.

        This method has id ``3.8``.

        - :cpp:expr:`state`: Output parameter.


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

