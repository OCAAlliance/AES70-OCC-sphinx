.. _ocamediaclock:

1.2.6  OcaMediaClock
====================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaMediaClock <ocamediaclock>` 

.. cpp:class:: OcaMediaClock: OcaAgent

     **DEPRECATED CLASS**   *Replaced by*  **OcaMediaClock3**  A media clock, internal or external.

    **Properties**:

    .. _ocamediaclock_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.6"

        This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocamediaclock_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocamediaclock_type:

    .. cpp:member:: OcaMediaClockType Type

        Type of clock.

        This property has id ``3.1``.

    .. _ocamediaclock_domainid:

    .. cpp:member:: OcaUint16 DomainID

        Clock domain ID. Arbitrary value.

        This property has id ``3.2``.

    .. _ocamediaclock_ratessupported:

    .. cpp:member:: OcaList<OcaMediaClockRate> RatesSupported

        List of supported rates

        This property has id ``3.3``.

    .. _ocamediaclock_currentrate:

    .. cpp:member:: OcaMediaClockRate CurrentRate

        Current clock rate

        This property has id ``3.4``.

    .. _ocamediaclock_lockstate:

    .. cpp:member:: OcaMediaClockLockState LockState

        Lock state of clock.

        This property has id ``3.5``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocamediaclock_gettype:

    .. cpp:function:: OcaStatus GetType(OcaMediaClockType &Type)

        Gets the value of the  **Type** property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.1``.

        :param OcaMediaClockType Type: Output parameter.

    .. _ocamediaclock_settype:

    .. cpp:function:: OcaStatus SetType(OcaMediaClockType Type)

        Sets the value of the  **Type** property. The return value indicates whether the value was successfully set. Optional method, may not be supported in all implementations.

        This method has id ``3.2``.

        :param OcaMediaClockType Type: Input parameter.

    .. _ocamediaclock_getdomainid:

    .. cpp:function:: OcaStatus GetDomainID(OcaUint16 &ID)

        Gets the value of the  **DomainID** property. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.3``.

        :param OcaUint16 ID: Output parameter.

    .. _ocamediaclock_setdomainid:

    .. cpp:function:: OcaStatus SetDomainID(OcaUint16 ID)

        Sets the value of the  **DomainID** property. The return value indicates whether the value was successfully set. Optional method, may not be supported in all implementations.

        This method has id ``3.4``.

        :param OcaUint16 ID: Input parameter.

    .. _ocamediaclock_getsupportedrates:

    .. cpp:function:: OcaStatus GetSupportedRates(OcaList<OcaMediaClockRate> &ID)

        Gets the list of supported sampling rates. The return value indicates whether the list was successfully retrieved.

        This method has id ``3.5``.

        :param OcaList<OcaMediaClockRate> ID: Output parameter.

    .. _ocamediaclock_getcurrentrate:

    .. cpp:function:: OcaStatus GetCurrentRate(OcaMediaClockRate &rate)

        Gets the current sampling rate. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.6``.

        :param OcaMediaClockRate rate: Output parameter.

    .. _ocamediaclock_setcurrentrate:

    .. cpp:function:: OcaStatus SetCurrentRate(OcaMediaClockRate rate)

        Sets the sampling rate. The return value indicates whether the rate was successfully set.

        This method has id ``3.7``.

        :param OcaMediaClockRate rate: Input parameter.

    .. _ocamediaclock_getlockstate:

    .. cpp:function:: OcaStatus GetLockState(OcaMediaClockLockState &state)

        Gets the current media clock lock state. The return value indicates whether the value was successfully retrieved.

        This method has id ``3.8``.

        :param OcaMediaClockLockState state: Output parameter.


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
    
    


