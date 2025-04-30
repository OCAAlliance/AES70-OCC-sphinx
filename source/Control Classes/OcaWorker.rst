.. _ocaworker:

1.1  OcaWorker
==============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>`

.. cpp:class:: OcaWorker: OcaRoot

    Abstract base class for classes that represent the device's application and
    support functions.

    **Properties**:


    .. _ocaworker_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaworker_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaworker_enabled:

    .. cpp:member:: OcaBoolean Enabled

        Read/write property that indicates whether the worker object is enabled
        in the device. If an object is disabled it cannot be used by the
        application. Note that the behavior of a disabled object depends on the
        object itself (e.g. a disabled signal generator is silent, a disabled
        equalizer is flat, etc.).

        This property has id ``2.1``.

    .. _ocaworker_label:

    .. cpp:member:: OcaString Label

        Specific label of the worker. Can be used to provide human readable
        information about the worker. The label can be get and set over the
        network.

        This property has id ``2.3``.

    .. _ocaworker_latency:

    .. cpp:member:: OcaTimeInterval Latency

        Processing latency of this object. Optional. Readonly or readwrite,
        depending on implementation.

        This property has id ``2.5``.

    .. _ocaworker_owner:

    .. cpp:member:: const OcaONo Owner

        Object number of block that contains this worker. Read-only.

        This property has id ``2.4``.

    .. _ocaworker_portclockmap:

    .. cpp:member:: OcaMap<OcaPortID, OcaPortClockMapEntry> PortClockMap

        **Optional property.** Map that connects OcaMediaClock3 object numbers
        to input and output OcaPorts and specifies sampling rate converters, if
        any. OcaPortID = {mode,index}, where mode = Input or Output. Map entries
        with index=0 are default values, to be used when no entry is found for a
        given port.

        This property has id ``2.6``.

    .. _ocaworker_ports:

    .. cpp:member:: OcaList<OcaPort> Ports

        The list of (input and output) OCA ports the worker object has. Note
        that a worker object can have no ports, in which case the list is empty.

        This property has id ``2.2``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocaworker_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        Gets the value of the Enabled property.

        This method has id ``2.1``.

        - :cpp:expr:`enabled`: Output parameter.


    .. _ocaworker_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        Sets the value of the Enabled property.

        This method has id ``2.2``.

        - :cpp:expr:`enabled`: Input parameter.


    .. _ocaworker_addport:

    .. cpp:function:: OcaStatus AddPort(OcaString Name, OcaIODirection Mode, OcaPortID &ID)

        Adds an input or output port..

        This method has id ``2.3``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`Mode`: Input parameter.


        - :cpp:expr:`ID`: Output parameter.


    .. _ocaworker_deleteport:

    .. cpp:function:: OcaStatus DeletePort(OcaPortID ID)

        Deletes an input or output port..

        This method has id ``2.4``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocaworker_getports:

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        Gets the list of ports owned by the Worker object.

        This method has id ``2.5``.

        - :cpp:expr:`OcaPorts`: Output parameter.


    .. _ocaworker_getportname:

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        Gets the name of the designated port.

        This method has id ``2.6``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Name`: Output parameter.


    .. _ocaworker_setportname:

    .. cpp:function:: OcaStatus SetPortName(OcaPortID ID, OcaString Name)

        Sets the name of the designated port.

        This method has id ``2.7``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Name`: Input parameter.


    .. _ocaworker_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &label)

        Gets the value of the Label property.

        This method has id ``2.8``.

        - :cpp:expr:`label`: Output parameter.


    .. _ocaworker_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString label)

        Sets the value of the Label property.

        This method has id ``2.9``.

        - :cpp:expr:`label`: Input parameter.


    .. _ocaworker_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        Gets the value of the Owner property.

        This method has id ``2.10``.

        - :cpp:expr:`owner`: Output parameter.


    .. _ocaworker_getlatency:

    .. cpp:function:: OcaStatus GetLatency(OcaTimeInterval &latency)

        Gets the value of the Latency property.

        This method has id ``2.11``.

        - :cpp:expr:`latency`: Output parameter.


    .. _ocaworker_setlatency:

    .. cpp:function:: OcaStatus SetLatency(OcaTimeInterval latency)

        Sets the value of the Latency property.

        This method has id ``2.12``.

        - :cpp:expr:`latency`: Input parameter.


    .. _ocaworker_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaRolePath &RolePath, OcaONoPath &ONoPath)

        Returns Role Path and ONo Path from the Root Block to this object. The
        return value indicates whether the operation succeeded.

        This method has id ``2.13``.

        - :cpp:expr:`RolePath`: Output parameter.


        - :cpp:expr:`ONoPath`: Output parameter.


    .. _ocaworker_getportclockmap:

    .. cpp:function:: OcaStatus GetPortClockMap(OcaMap<OcaPortID, OcaPortClockMapEntry> &Map)

        Gets the value of the PortClockMap property.

        This method has id ``2.14``.

        - :cpp:expr:`Map`: Output parameter.


    .. _ocaworker_setportclockmap:

    .. cpp:function:: OcaStatus SetPortClockMap(OcaMap<OcaPortID, OcaPortClockMapEntry> Map)

        Sets the value of the PortClockMap property.

        This method has id ``2.15``.

        - :cpp:expr:`Map`: Input parameter.


    .. _ocaworker_getportclockmapentry:

    .. cpp:function:: OcaStatus GetPortClockMapEntry(OcaPortID ID, OcaPortClockMapEntry &Entry)

        Gets the value of the PortClockMap entry identified by the given PortID.

        This method has id ``2.16``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Entry`: Output parameter.


    .. _ocaworker_setportclockmapentry:

    .. cpp:function:: OcaStatus SetPortClockMapEntry(OcaPortID PortID, OcaPortClockMapEntry Entry)

        Sets an entry in the PortClockMap property. Adds entry if none already
        exists for the given port; replaces entry if it does already exist.

        This method has id ``2.17``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Entry`: Input parameter.


    .. _ocaworker_deleteportclockmapentry:

    .. cpp:function:: OcaStatus DeletePortClockMapEntry(OcaPortID ID)

        Deletes PortClockMap entry identified by the given ID.

        This method has id ``2.18``.

        - :cpp:expr:`ID`: Input parameter.


    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaRoot::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

