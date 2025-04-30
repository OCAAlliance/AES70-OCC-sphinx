.. _ocanetworkapplication:

1.7  OcaNetworkApplication
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaNetworkApplication <ocanetworkapplication>`

.. cpp:class:: OcaNetworkApplication: OcaRoot

    Base class for network applications

    **Properties**:


    .. _ocanetworkapplication_adaptationdata:

    .. cpp:member:: OcaAdaptationData AdaptationData

        Adaptation-specific data, if any

        This property has id ``2.5``.

    .. _ocanetworkapplication_adaptationidentifier:

    .. cpp:member:: const OcaAdaptationIdentifier AdaptationIdentifier

        Null string in the base class. Value will be overridden in child classes
        by the identifier of the Adaptation that defined the respective child
        class. Read-only.

        This property has id ``2.4``.

    .. _ocanetworkapplication_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.7"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocanetworkapplication_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocanetworkapplication_label:

    .. cpp:member:: OcaString Label

        User-defined label. No programmatic significance. Read/write.

        This property has id ``2.1``.

    .. _ocanetworkapplication_networkinterfaceassignments:

    .. cpp:member:: OcaList<OcaNetworkInterfaceAssignment> NetworkInterfaceAssignments

        List of network interface assignments that bind this application network
        to one or more network interfaces.

        This property has id ``2.3``.

    .. _ocanetworkapplication_owner:

    .. cpp:member:: const OcaONo Owner

        Object number of block that contains this object. Read-only.

        This property has id ``2.2``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocanetworkapplication_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the value of the **Label** property.

        This method has id ``2.1``.

        - :cpp:expr:`Label`: Output parameter.


    .. _ocanetworkapplication_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the value of the **Label** property.

        This method has id ``2.2``.

        - :cpp:expr:`Label`: Input parameter.


    .. _ocanetworkapplication_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        Gets the value of the **Owner** property.

        This method has id ``2.3``.

        - :cpp:expr:`Owner`: Output parameter.


    .. _ocanetworkapplication_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaRolePath &RolePath, OcaONoPath &ONoPath)

        Returns Role Path and ONo Path from the Root Block to this object. The
        return value indicates whether the operation succeeded.

        This method has id ``2.4``.

        - :cpp:expr:`RolePath`: Output parameter.


        - :cpp:expr:`ONoPath`: Output parameter.


    .. _ocanetworkapplication_getnetworkinterfaceassignments:

    .. cpp:function:: OcaStatus GetNetworkInterfaceAssignments(OcaList<OcaNetworkInterfaceAssignment> &Assignments)

        Gets the list of network interface assignments

        This method has id ``2.5``.

        - :cpp:expr:`Assignments`: Output parameter.


    .. _ocanetworkapplication_setnetworkinterfaceassignments:

    .. cpp:function:: OcaStatus SetNetworkInterfaceAssignments(OcaList<OcaNetworkInterfaceAssignment> Assignments)

        Sets the list of network interface assignments

        This method has id ``2.6``.

        - :cpp:expr:`Assignments`: Input parameter.


    .. _ocanetworkapplication_getadaptationidentifier:

    .. cpp:function:: OcaStatus GetAdaptationIdentifier(OcaString &Identifier)

        Gets the identifier of the Adaptation this network object implements.

        This method has id ``2.7``.

        - :cpp:expr:`Identifier`: Output parameter.


    .. _ocanetworkapplication_getadaptationdata:

    .. cpp:function:: OcaStatus GetAdaptationData(OcaAdaptationData &Data)

        Gets the value of property **AdaptationData.**

        This method has id ``2.8``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocanetworkapplication_setadaptationdata:

    .. cpp:function:: OcaStatus SetAdaptationData(OcaAdaptationData Data)

        Sets the value of property **AdaptationData.**

        This method has id ``2.9``.

        - :cpp:expr:`Data`: Input parameter.


    .. _ocanetworkapplication_getcounterset:

    .. cpp:function:: OcaStatus GetCounterSet(OcaCounterSet &CounterSet)

        Get this object's CounterSet.

        This method has id ``2.10``.

        - :cpp:expr:`CounterSet`: Output parameter.


    .. _ocanetworkapplication_getcounter:

    .. cpp:function:: OcaStatus GetCounter(OcaID16 CounterID, OcaCounter &Counter)

        Gets the given counter from this object's CounterSet.

        This method has id ``2.11``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`Counter`: Output parameter.


    .. _ocanetworkapplication_attachcounternotifier:

    .. cpp:function:: OcaStatus AttachCounterNotifier(OcaID16 CounterID, OcaONo ONo)

        Adds a notifier **ONo** to the **Notifiers** list of the designated
        Counter.

        This method has id ``2.12``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`ONo`: Input parameter.


    .. _ocanetworkapplication_detachcounternotifier:

    .. cpp:function:: OcaStatus DetachCounterNotifier(OcaID16 CounterID, OcaONo ONo)

        Removes the given notifier ONo from the **Notifiers** list of the
        designated counter.

        This method has id ``2.13``.

        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`ONo`: Input parameter.


    .. _ocanetworkapplication_resetcounters:

    .. cpp:function:: OcaStatus ResetCounters()

        Reset this object's CounterSet. Sets all its counters to their specified
        initial values.

        This method has id ``2.14``.

    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaRoot::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

