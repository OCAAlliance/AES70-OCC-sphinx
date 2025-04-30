.. _ocastreamconnector:

1.2.11  OcaStreamConnector
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaStreamConnector <ocastreamconnector>`

.. cpp:class:: OcaStreamConnector: OcaAgent

    **DEPRECATED CLASS** *Replaced by the* **OcaMediaSinkConnector ** *and*
    **OcaMediaSourceConnector ** *datatypes in version 3 of Connection
    Management (CM3)* Agent class for objects ("connectors") that allow
    connection of streams to the device. Streams may be single channels or
    multichannel groups. A connector is either a *source* or a *sink.* Sources
    are sometimes called "talkers". Sinks are sometimes called "listeners". Each
    connector links to zero or more **OcaStream** data objects. Each
    **OcaStream** object represents a signal flow to or from a local connector
    to a remote connector. The remote connector is usually, but not necessarily,
    in a different node. Each connector collects zero or more *signal channels*.
    A signal channel is an instance of **OcaNetworkSignalChannel.** Each signal
    channel exposes one media channel of the stream to the interior of the
    device. A signal channel therefore is a Worker that contains exactly one
    **OcaPort** data object. Each **OcaStreamConnector** object belongs to a
    particular instance of **OcaStreamNetwork** or a subclass of
    **OcaStreamNetwork** **.** Each **OcaStreamConnector** is linked to its
    network through the **Owner** property.

     - When a controller creates an **OcaStreamConnector** object dynamically,
       the controller must store the Object Number of the corresponding
       **OcaStreamNetwork** object in the **Owner** property.

     - Upon receiving the **Owner** property change, the **OcaStreamConnector**
       object must register itself with the given stream network object via some
       internal means.


    This class may be subclassed to support various network types. ** **

    **Properties**:


    .. _ocastreamconnector_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.11"

        ID of this class

        This property has id ``1.1``.

    .. _ocastreamconnector_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Version number of this class

        This property has id ``1.2``.

    .. _ocastreamconnector_idadvertised:

    .. cpp:member:: OcaStreamConnectorID IDAdvertised

        Character name or binary identifier of this connector. This ID is
        advertised on the network to be found by other devices' discovery
        processes.

        This property has id ``3.2``.

    .. _ocastreamconnector_ownernetwork:

    .. cpp:member:: OcaONo OwnerNetwork

        Object number of stream network object (**OcaStreamNetwork** or one of
        its subclasses) to which this connector belongs. In reconfigurable
        devices, a controller that creates an **OcaStreamConnector** object must
        store the appropriate stream network object number into this property.
        It is assumed that, upon receiving a value into its **Owner** property,
        the terminus object will by internal means register itself with the
        identified stream network.

        This property has id ``3.1``.

    .. _ocastreamconnector_pins:

    .. cpp:member:: OcaMap<OcaStreamConnectorPinIndex, OcaONo> Pins

        The map of connector pin indexes to
        **OcaNetworkSignalChannel[Source|Sink]** objects collected by this
        connector. The pin indexes are fixed indexes 1 to n, where n is the
        number of channels the connector accommodates (determined when the
        connector is created). If a certain pin in the connector is currently
        not attached the OcaONo of that index is 0.

        This property has id ``3.5``.

    .. _ocastreamconnector_sourceorsink:

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        Specifies whether this connector is for output (source) or input (sink)
        signal channels.

        This property has id ``3.3``.

    .. _ocastreamconnector_status:

    .. cpp:member:: OcaStreamConnectorStatus Status

        Status of this terminus.

        This property has id ``3.6``.

    .. _ocastreamconnector_streams:

    .. cpp:member:: OcaMap<OcaStreamIndex, OcaStream> Streams

        The list of **OcaStream** data objects contained in (i.e. connected to)
        this connector.

        This property has id ``3.4``.

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


    .. _ocastreamconnector_getownernetwork:

    .. cpp:function:: OcaStatus GetOwnerNetwork(OcaONo &Network)

        Gets the object number of the **OcaStreamNetwork** object to which this
        connector belongs. Return status indicates success of operation.

        This method has id ``3.1``.

        - :cpp:expr:`Network`: Output parameter.


    .. _ocastreamconnector_setownernetwork:

    .. cpp:function:: OcaStatus SetOwnerNetwork(OcaONo Network)

        Sets the object number of the **OcaStreamNetwork** object to which this
        connector belongs. Return status indicates success of operation. Only
        implemented for reconfigurable devices.

        This method has id ``3.2``.

        - :cpp:expr:`Network`: Input parameter.


    .. _ocastreamconnector_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaStreamConnectorID &IDAdvertised)

        Gets the value of the IDAdvertised property. Return status indicates
        success of operation.

        This method has id ``3.3``.

        - :cpp:expr:`IDAdvertised`: Output parameter.


    .. _ocastreamconnector_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaStreamConnectorID IDAdvertised)

        Sets the value of the IDAdvertised property. Return status indicates
        success of operation.

        This method has id ``3.4``.

        - :cpp:expr:`IDAdvertised`: Input parameter.


    .. _ocastreamconnector_getsourceorsink:

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        Gets the value of the SourceOrSink property. Return status indicates
        success of operation.

        This method has id ``3.5``.

        - :cpp:expr:`SourceOrSink`: Output parameter.


    .. _ocastreamconnector_setsourceorsink:

    .. cpp:function:: OcaStatus SetSourceOrSink(OcaNetworkMediaSourceOrSink SourceOrSink)

        Sets the value of the SourceOrSink property. Return status indicates
        success of operation. Only implemented for reconfigurable devices. Note
        that this method can only be called when the SignalChannels property is
        empty, i.e. does not contain any actual channels.

        This method has id ``3.6``.

        - :cpp:expr:`SourceOrSink`: Input parameter.


    .. _ocastreamconnector_connectstream:

    .. cpp:function:: OcaStatus ConnectStream(OcaStream Stream, OcaStreamIndex &Index)

        Connects a stream to this connector. Return status indicates success of
        operation.

        This method has id ``3.7``.

        - :cpp:expr:`Stream`: Input parameter.


        - :cpp:expr:`Index`: Output parameter.


    .. _ocastreamconnector_disconnectstream:

    .. cpp:function:: OcaStatus DisconnectStream(OcaStreamIndex StreamID)

        Disconnects a stream from this connector. Return status indicates
        success of operation.

        This method has id ``3.8``.

        - :cpp:expr:`StreamID`: Input parameter.


    .. _ocastreamconnector_getstreams:

    .. cpp:function:: OcaStatus GetStreams(OcaMap<OcaStreamIndex, OcaStream> &Streams)

        Gets the map of OcaStream items connected to this connector. Return
        status indicates success of operation.

        This method has id ``3.9``.

        - :cpp:expr:`Streams`: Output parameter.


    .. _ocastreamconnector_getpins:

    .. cpp:function:: OcaStatus GetPins(OcaMap<OcaStreamConnectorPinIndex, OcaONo> &Pins)

        Gets the list of object numbers of **OcaNetworkSignalChannel** objects
        connected to this connector. Return status indicates success of
        operation.

        This method has id ``3.10``.

        - :cpp:expr:`Pins`: Output parameter.


    .. _ocastreamconnector_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaStreamConnectorStatus &Status)

        Gets the value of the Status property. Return status indicates success
        of operation.

        This method has id ``3.11``.

        - :cpp:expr:`Status`: Output parameter.


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

