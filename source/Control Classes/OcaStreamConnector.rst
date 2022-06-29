.. _ocastreamconnector:

1.2.11  OcaStreamConnector
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaStreamConnector <ocastreamconnector>` 

.. cpp:class:: OcaStreamConnector: OcaAgent

     **DEPRECATED CLASS**   *Replaced by the*  **OcaMediaSinkConnector **  *and*  **OcaMediaSourceConnector **  *datatypes in version 3 of Connection Management (CM3)*  Agent class for objects ("connectors") that allow connection of streams to the device. Streams may be single channels or multichannel groups. A connector is either a  *source*  or a  *sink.*  Sources are sometimes called "talkers". Sinks are sometimes called "listeners". Each connector links to zero or more  **OcaStream**  data objects. Each  **OcaStream**  object represents a signal flow to or from a local connector to a remote connector. The remote connector is usually, but not necessarily, in a different node. Each connector collects zero or more  *signal channels* . A signal channel is an instance of  **OcaNetworkSignalChannel.**  Each signal channel exposes one media channel of the stream to the interior of the device. A signal channel therefore is a Worker that contains exactly one  **OcaPort**  data object. Each  **OcaStreamConnector** object belongs to a particular instance of  **OcaStreamNetwork**  or a subclass of  **OcaStreamNetwork**   **.**  Each  **OcaStreamConnector** is linked to its network through the  **Owner**  property.  
    
     - When a controller creates an  **OcaStreamConnector** object dynamically, the controller must store the Object Number of the corresponding  **OcaStreamNetwork** object in the  **Owner**  property.
     
    
     - Upon receiving the  **Owner**  property change, the  **OcaStreamConnector** object must register itself with the given stream network object via some internal means.
      This class may be subclassed to support various network types. 

    **Properties**:

    .. _ocastreamconnector_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.11"

        ID of this class

        This property has id ``3.1``.

    .. _ocastreamconnector_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Version number of this class

        This property has id ``3.2``.

    .. _ocastreamconnector_idadvertised:

    .. cpp:member:: OcaStreamConnectorID IDAdvertised

        Character name or binary identifier of this connector. This ID is advertised on the network to be found by other devices' discovery processes.

        This property has id ``3.2``.

    .. _ocastreamconnector_ownernetwork:

    .. cpp:member:: OcaONo OwnerNetwork

        Object number of stream network object ( **OcaStreamNetwork**  or one of its subclasses) to which this connector belongs. In reconfigurable devices, a controller that creates an  **OcaStreamConnector** object must store the appropriate stream network object number into this property. It is assumed that, upon receiving a value into its  **Owner**  property, the terminus object will by internal means register itself with the identified stream network.

        This property has id ``3.1``.

    .. _ocastreamconnector_pins:

    .. cpp:member:: OcaMap<OcaStreamConnectorPinIndex, OcaONo> Pins

        The map of connector pin indexes to  **OcaNetworkSignalChannel[Source|Sink]** objects collected by this connector. The pin indexes are  _fixed indexes_  1 to n, where n is the number of channels the connector accommodates (determined when the connector is created). If a certain pin in the connector is currently not attached the OcaONo of that index is 0.

        This property has id ``3.5``.

    .. _ocastreamconnector_sourceorsink:

    .. cpp:member:: OcaNetworkMediaSourceOrSink SourceOrSink

        Specifies whether this connector is for output (source) or input (sink) signal channels.

        This property has id ``3.3``.

    .. _ocastreamconnector_status:

    .. cpp:member:: OcaStreamConnectorStatus Status

        Status of this terminus.

        This property has id ``3.6``.

    .. _ocastreamconnector_streams:

    .. cpp:member:: OcaMap<OcaStreamIndex, OcaStream> Streams

        The list of  **OcaStream** data objects contained in (i.e. connected to) this connector.

        This property has id ``3.4``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocastreamconnector_connectstream:

    .. cpp:function:: OcaStatus ConnectStream(OcaStream Stream, OcaStreamIndex &Index)

        Connects a stream to this connector. Return status indicates success of operation.

        This method has id ``3.7``.

        :param OcaStream Stream: Input parameter.
        :param OcaStreamIndex Index: Output parameter.

    .. _ocastreamconnector_disconnectstream:

    .. cpp:function:: OcaStatus DisconnectStream(OcaStreamIndex StreamID)

        Disconnects a stream from this connector. Return status indicates success of operation.

        This method has id ``3.8``.

        :param OcaStreamIndex StreamID: Input parameter.

    .. _ocastreamconnector_getidadvertised:

    .. cpp:function:: OcaStatus GetIDAdvertised(OcaStreamConnectorID &IDAdvertised)

        Gets the value of the IDAdvertised property. Return status indicates success of operation.

        This method has id ``3.3``.

        :param OcaStreamConnectorID IDAdvertised: Output parameter.

    .. _ocastreamconnector_getownernetwork:

    .. cpp:function:: OcaStatus GetOwnerNetwork(OcaONo &Network)

        Gets the object number of the  **OcaStreamNetwork** object to which this connector belongs. Return status indicates success of operation.

        This method has id ``3.1``.

        :param OcaONo Network: Output parameter.

    .. _ocastreamconnector_getpins:

    .. cpp:function:: OcaStatus GetPins(OcaMap<OcaStreamConnectorPinIndex, OcaONo> &Pins)

        Gets the list of object numbers of  **OcaNetworkSignalChannel** objects connected to this connector. Return status indicates success of operation.

        This method has id ``3.10``.

        :param OcaMap<OcaStreamConnectorPinIndex, OcaONo> Pins: Output parameter.

    .. _ocastreamconnector_getsourceorsink:

    .. cpp:function:: OcaStatus GetSourceOrSink(OcaNetworkMediaSourceOrSink &SourceOrSink)

        Gets the value of the SourceOrSink property. Return status indicates success of operation.

        This method has id ``3.5``.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Output parameter.

    .. _ocastreamconnector_getstatus:

    .. cpp:function:: OcaStatus GetStatus(OcaStreamConnectorStatus &Status)

        Gets the value of the Status property. Return status indicates success of operation.

        This method has id ``3.11``.

        :param OcaStreamConnectorStatus Status: Output parameter.

    .. _ocastreamconnector_getstreams:

    .. cpp:function:: OcaStatus GetStreams(OcaMap<OcaStreamIndex, OcaStream> &Streams)

        Gets the map of OcaStream items connected to this connector. Return status indicates success of operation.

        This method has id ``3.9``.

        :param OcaMap<OcaStreamIndex, OcaStream> Streams: Output parameter.

    .. _ocastreamconnector_setidadvertised:

    .. cpp:function:: OcaStatus SetIDAdvertised(OcaStreamConnectorID IDAdvertised)

        Sets the value of the IDAdvertised property. Return status indicates success of operation.

        This method has id ``3.4``.

        :param OcaStreamConnectorID IDAdvertised: Input parameter.

    .. _ocastreamconnector_setownernetwork:

    .. cpp:function:: OcaStatus SetOwnerNetwork(OcaONo Network)

        Sets the object number of the  **OcaStreamNetwork** object to which this connector belongs. Return status indicates success of operation. Only implemented for reconfigurable devices.

        This method has id ``3.2``.

        :param OcaONo Network: Input parameter.

    .. _ocastreamconnector_setsourceorsink:

    .. cpp:function:: OcaStatus SetSourceOrSink(OcaNetworkMediaSourceOrSink SourceOrSink)

        Sets the value of the SourceOrSink property. Return status indicates success of operation. Only implemented for reconfigurable devices. Note that this method can only be called when the SignalChannels property is empty, i.e. does not contain any actual channels.

        This method has id ``3.6``.

        :param OcaNetworkMediaSourceOrSink SourceOrSink: Input parameter.


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
    
    


