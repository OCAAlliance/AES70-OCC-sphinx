*****************
Counter Datatypes
*****************

.. _OcaCounter:

OcaCounter
==========

.. cpp:struct:: OcaCounter

    A general-purpose Counter. See [AES70-1(Counters and Countersets)].

    .. cpp:member:: OcaID16 ID

        Counter identifier. Unique within enclosing Counterset.

    .. cpp:member:: OcaUint64 Value

        The count.

    .. cpp:member:: OcaUint64 InitialValue

        Value that a reset sets in the Counter.

    .. cpp:member:: OcaString Role

        Readonly name of Counter's function in context. Values beginning with
        "oca" in any character case shall be reserved for AES use.

    .. cpp:member:: OcaList<OcaONo> Notifiers

        List of ONos of Notifiers attached to this Counter. May be empty.

.. _OcaCounterSet:

OcaCounterSet
=============

.. cpp:struct:: OcaCounterSet

    A set of Counters

    .. cpp:member:: OcaCounterSetID ID

        Nonvolatile, unique identifier of this Counterset within this Device.

    .. cpp:member:: OcaList<OcaCounter> Counters

        List of Counters in this Counterset.

.. _OcaCounterSetID:

OcaCounterSetID
===============

.. cpp:type:: OcaCounterSetID = OcaBlob

    Nonvolatile, unique identifier of a Counterset within a Device

.. _OcaCounterNotifierFilterParameters:

OcaCounterNotifierFilterParameters
==================================

.. cpp:struct:: OcaCounterNotifierFilterParameters

    Filter parameters for **OcaCountersetNotifier**.

    .. cpp:member:: OcaUint64 Threshold

        Threshold comparison value. If **Operator** is zero, no threshold test
        is performed. See description of class **OcaCounterNotifier**.

    .. cpp:member:: OcaRelationalOperator Operator

        Type of threshold comparison. See description of class
        **OcaCounterNotifier**.

    .. cpp:member:: OcaTimeInterval Period

        Period for periodic updates, in seconds. Zero value means no periodic
        updates. See description of class **OcaCounterNotifier.**

    .. cpp:member:: OcaUint64 CountDelta

        Count increment for "every-n-counts" updates. Absolute value, applies
        when counter changes by +n or -n. Zero value means no "every-n"
        notifications. See description of class **OcaCounterNotifier.**

.. _OcaCounterUpdate:

OcaCounterUpdate
================

.. cpp:struct:: OcaCounterUpdate

    Descriptor of a Counter update, used by **OcaCounterNotifier**, in its
    **CounterUpdate()** event and its **GetLastUpdate()** method.

    .. cpp:member:: OcaCounterSetID CounterSetID

        Identifies Counterset within Device.

    .. cpp:member:: OcaID16 CounterID

        Identifies Counter within Counterset.

    .. cpp:member:: OcaUint64 Value

        The Counter's value.

