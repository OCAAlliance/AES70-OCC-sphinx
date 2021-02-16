***************
Agent Datatypes
***************

.. _OcaGrouperGroup:

OcaGrouperGroup
===============

.. cpp:struct:: OcaGrouperGroup
    
    Describes a group in a grouper.

    .. cpp:member:: OcaUint16 Index

        Index of group in Grouper

    .. cpp:member:: OcaString Name

        Name of the group.

    .. cpp:member:: OcaONo ProxyONo

        Object number of the group's proxy. The proxy's class is the same as
        the Grouper's citizen class.


OCP.1 Encoding
--------------

============ ========== ===========
Field        Basic type Byte length
============ ========== ===========
Index        OcaUint16  2          
Name.Len     OcaUint16  2          
Name.Value   string     variable   
ProxyONo.ONo OcaUint32  4          
============ ========== ===========


.. _OcaGrouperCitizen:

OcaGrouperCitizen
=================

.. cpp:struct:: OcaGrouperCitizen
    
    Describes a citizen of a grouper. Refers to a specific worker object
    somewhere in the media network.

    .. cpp:member:: OcaUint16 Index

        Index of citizen in Grouper

    .. cpp:member:: OcaOPath ObjectPath

        Object path (= hostname + object number) of the worker object that is
        the citizen of the grouper.

    .. cpp:member:: OcaBoolean Online

        True iff connection from grouper to citizen is healthy.


OCP.1 Encoding
--------------

================== ================ ===========
Field              Basic type       Byte length
================== ================ ===========
Index              OcaUint16        2          
ObjectPath.HostID  OcaNetworkHostID variable   
ObjectPath.ONo.ONo OcaUint32        4          
Online             OcaBoolean       1          
================== ================ ===========


.. _OcaGrouperEnrollment:

OcaGrouperEnrollment
====================

.. cpp:struct:: OcaGrouperEnrollment
    
    Describes the enrollment of a citizen into a group.

    .. cpp:member:: OcaUint16 GroupIndex

        Grouper's index of group in which the citizen identified by
        CitizenIndex is enrolled.

    .. cpp:member:: OcaUint16 CitizenIndex

        Grouper's index of a citizen enrolled in the group identified by
        GroupIndex.


OCP.1 Encoding
--------------

============ ========== ===========
Field        Basic type Byte length
============ ========== ===========
GroupIndex   OcaUint16  2          
CitizenIndex OcaUint16  2          
============ ========== ===========


.. _OcaGrouperMode:

OcaGrouperMode
==============

.. cpp:enum-struct:: OcaGrouperMode

    Select mode of **OcaGrouper** : master-slave or peer-to-peer

    .. cpp:enumerator:: MasterSlave = 1

        OcaGrouper is in master-slave mode.
    .. cpp:enumerator:: PeerToPeer = 2

        OcaGrouper is in peer-to-peer mode.
.. _OcaObserverState:

OcaObserverState
================

.. cpp:enum-struct:: OcaObserverState

    Interpolation law for ramper to use.

    .. cpp:enumerator:: NotTriggered = 0

        Observer is not triggered.
    .. cpp:enumerator:: Triggered = 1

        Observer is triggered.
.. _OcaRelationalOperator:

OcaRelationalOperator
=====================

.. cpp:enum-struct:: OcaRelationalOperator

    Enumeration of relational operators that can be used in OCA classes.

    .. cpp:enumerator:: None = 0

    .. cpp:enumerator:: Equality = 1

        The equality (==) operator.
    .. cpp:enumerator:: Inequality = 2

        The inequality (!=) operator.
    .. cpp:enumerator:: GreaterThan = 3

        The greater than (&gt;) operator.
    .. cpp:enumerator:: GreaterThanOrEqual = 4

        The greater than or equal (&gt;=) operator.
    .. cpp:enumerator:: LessThan = 5

        The less than (&lt;) operator
    .. cpp:enumerator:: LessThanOrEqual = 6

        The less than or equal (&lt;=) operator.
.. _OcaPowerSupplyType:

OcaPowerSupplyType
==================

.. cpp:enum-struct:: OcaPowerSupplyType

    Type of power supply.

    .. cpp:enumerator:: None = 0

        No power supply.
    .. cpp:enumerator:: Mains = 1

        Mains-powered power supply.
    .. cpp:enumerator:: Battery = 2

        Battery power supply.
    .. cpp:enumerator:: Phantom = 3

        Phantom power supply. Includes Power-over-Ethernet supplies.
    .. cpp:enumerator:: Solar = 4

        Solar power supply
.. _OcaPowerSupplyLocation:

OcaPowerSupplyLocation
======================

.. cpp:enum-struct:: OcaPowerSupplyLocation

    Physical location of a device power supply.

    .. cpp:enumerator:: Unspecified = 1

        Unspecified location
    .. cpp:enumerator:: Internal = 2

        Power supply is physically inside the device.
    .. cpp:enumerator:: External = 3

        Power supply is physically outside the device.
.. _OcaPowerSupplyState:

OcaPowerSupplyState
===================

.. cpp:enum-struct:: OcaPowerSupplyState

    Status of a device power supply.

    .. cpp:enumerator:: Off = 0

        Powered down.
    .. cpp:enumerator:: Unavailable = 1

        Power supply is turned on but not available for activation.
    .. cpp:enumerator:: Available = 2

        Power supply is fully available for activation.
    .. cpp:enumerator:: Active = 3

        Power supply is currently supplying power to the device.
.. _OcaRamperCommand:

OcaRamperCommand
================

.. cpp:enum-struct:: OcaRamperCommand

    Command repertoire of OcaRamper's **Control** method.

    .. cpp:enumerator:: Enable = 1

        Enable the ramper. Enter **Enabled** state.
    .. cpp:enumerator:: Start = 2

        Unconditionally start ramping now. Enter **Ramping** state.
    .. cpp:enumerator:: Halt = 3

        If **Ramping** , stop ramping. Return to **Initialized** or
        **Scheduled** state, whichever is appropriate. Else return to
.. _OcaRamperState:

OcaRamperState
==============

.. cpp:enum-struct:: OcaRamperState

    States of the ramper. Here are the rules for ramper state change:
    
    - A freshly-constructed ramper's state is **NotInitialized** .
    
    
    - A ramper becomes **Initialized** when : The ramper is
    **NotInitialized** ; AND **TargetProperty** has been set to a valid
    value; AND **Goal** has been set; AND **Duration** has been set.
    
    
    - A ramper becomes **Scheduled** when It is **Initialized** ; AND
    **T** **start** and **TimeMode** have been set; AND (Tstart +
    **Duration** ) is in the future.
    
    
    - A ramper becomes **Enabled** when it is **Scheduled** AND receives
    an *Enable* command.
    
    
    - A ramper becomes **Ramping** when: It is **Enabled** and the ramp
    start time is reached; OR It is **Initialized** , **Scheduled** , or
    **Enabled** and a *Start* command is received.
    
    
    - Completion of a ramp or Receipt of a *Halt* command causes the state
    to become: **Scheduled** , if Tstart, Time Mode have been set; AND
    (Tstart + Duration) is in the future. Otherwise, **Initialized.**
    

    .. cpp:enumerator:: NotInitialized = 1

        Ramper is not initialized and may not be started or enabled.
    .. cpp:enumerator:: Iniitialized = 2

        Ramper is initialized sufficiently for nonscheduled ramps to work. A
        nonscheduled ramp is one that has no defined start time and must be
        started with the *Start* command.
    .. cpp:enumerator:: Scheduled = 3

        Ramper is initialized sufficiently for both nonscheduled and scheduled
        ramps to work. A scheduled ramp is one that has a defined start time.
    .. cpp:enumerator:: Enabled = 4

        Ramper's timer is running and scheduled ramp will commence at the
        designated future time.
    .. cpp:enumerator:: Ramping = 5

        Ramper is currently executing a ramp.