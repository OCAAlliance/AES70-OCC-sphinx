*****************
Network Datatypes
*****************

.. _OcaNetworkAddress:

OcaNetworkAddress
=================

.. cpp:type:: OcaNetworkAddress = OcaBlob

    Generic network address.
.. _OcaNetworkLinkType:

OcaNetworkLinkType
==================

.. cpp:enum:: OcaNetworkLinkType : uint8_t

    Types of layer 2 networks.

    .. cpp:enumerator:: None = 0

        No network
    .. cpp:enumerator:: EthernetWired = 1

        Wired Ethernet
    .. cpp:enumerator:: EthernetWireless = 2

        Wireless Ethernet
    .. cpp:enumerator:: USB = 3

        USB
    .. cpp:enumerator:: SerialP2P = 4

        Low-speed serial point-to-point
.. _OcaApplicationNetworkServiceID:

OcaApplicationNetworkServiceID
==============================

.. cpp:type:: OcaApplicationNetworkServiceID = OcaBlob

    Generic host ID.
.. _OcaNetworkSystemInterfaceDescriptor:

OcaNetworkSystemInterfaceDescriptor
===================================

.. cpp:struct:: OcaNetworkSystemInterfaceDescriptor
    
    Descriptor of a system interface used by a network. Format is data network type dependent.

    .. cpp:member:: OcaBlob SystemInterfaceParameters

        Parameters for the operating system interface the network uses to do I/O.

    .. cpp:member:: OcaNetworkAddress MyNetworkAddress

        The data network address that corresponds to this system interface.


OCP.1 Encoding
--------------

================================== ========== ===========
Field                              Basic type Byte length
================================== ========== ===========
SystemInterfaceParameters.DataSize OcaUint16  2          
SystemInterfaceParameters.Data     OcaUint8   1 * Count  
MyNetworkAddress.Value.DataSize    OcaUint16  2          
MyNetworkAddress.Value.Data        OcaUint8   1 * Count  
================================== ========== ===========


.. _OcaApplicationNetworkState:

OcaApplicationNetworkState
==========================

.. cpp:enum:: OcaApplicationNetworkState : uint8_t

    Network states.

    .. cpp:enumerator:: Unknown = 0

        State is not known.
    .. cpp:enumerator:: NotReady = 1

        Application network is not connected to host data network and is therefore not ready for connection establishng or application data transfer.
    .. cpp:enumerator:: Readying = 2

        Application network is in the process of connecting to the host data network and is therefore not ready for connection establishing or application data transfer.
    .. cpp:enumerator:: Ready = 3

        Application network is connected to host data network and is ready for connection establishing and application data transfer.
    .. cpp:enumerator:: Running = 4

        Application network is connected to host data network and is executing connection establishment and application data transfer.
    .. cpp:enumerator:: Paused = 5

        All application data transfer is paused, but connections are still in place.
    .. cpp:enumerator:: Stopping = 6

        Network is in the process of stopping all media application data transport activity and is deleting all media transport connections.
    .. cpp:enumerator:: Stopped = 7

        No application data transport connections exist, but application network is still connected to host data network.
    .. cpp:enumerator:: Fault = 8

        Application network has ceased all activity due to an error, but operating storage elements have not been freed.
.. _OcaApplicationNetworkCommand:

OcaApplicationNetworkCommand
============================

.. cpp:enum:: OcaApplicationNetworkCommand : uint8_t

    Command values for OcaMediaNetwork.Control().

    .. cpp:enumerator:: None = 0

        No-op. State is not changed.
    .. cpp:enumerator:: Prepare = 1

        Open a connection to the host data network, but do not make any media connections. Resulting state = Ready.
    .. cpp:enumerator:: Start = 2

        Commence media data connection-making and data transfer. Resulting state = Running.
    .. cpp:enumerator:: Pause = 3

        Temporarily halt all media data transfer, but preserve media connections. Resulting state = Paused. nb To unpause, a Start command should be used.
    .. cpp:enumerator:: Stop = 4

        Cease data transfer and delete all media connections. Resulting state = Stopped.
    .. cpp:enumerator:: Reset = 5

        Cease all media transfer, delete all media transport connections, and disconnect from the host data network. Resulting state = NotReady.
.. _OcaNetworkMediaProtocol:

OcaNetworkMediaProtocol
=======================

.. cpp:enum:: OcaNetworkMediaProtocol : uint8_t

    Media transport protocols available.

    .. cpp:enumerator:: None = 0

        No media protocol - the network does not do media transport.
    .. cpp:enumerator:: AV3 = 1

        AVnu AV3 - RTP over AVB
    .. cpp:enumerator:: AVBTP = 2

        IEEE 1722 / 1722.1
    .. cpp:enumerator:: Dante = 3

        Pre-AV3 Dante with ATP transport
    .. cpp:enumerator:: Cobranet = 4

        Cobranet
    .. cpp:enumerator:: AES67 = 5

        AES67 network.
    .. cpp:enumerator:: SMPTEAudio = 6

        SMPTE 2022? Or 2071? (TBD)
    .. cpp:enumerator:: LiveWire = 7

        LiveWire media transport
    .. cpp:enumerator:: ExtensionPoint = 65

        Base value for addition of nonstandard (e.g. proprietary) protocol options
.. _OcaNetworkControlProtocol:

OcaNetworkControlProtocol
=========================

.. cpp:enum:: OcaNetworkControlProtocol : uint8_t

    Network control protocols available.

    .. cpp:enumerator:: None = 0

        No control protocol - the network does not do control.
    .. cpp:enumerator:: OCP01 = 1

        OCP.1 - OCA protocol for TCP/IP networks
    .. cpp:enumerator:: OCP02 = 2

        OCP.2 - OCA protocol for USB links.
    .. cpp:enumerator:: OCP03 = 3

        OCP.3 - Character XML or JSON (tbd) version of OCA protocol, for serial links and other purposes.
.. _OcaMediaSinkConnector:

OcaMediaSinkConnector
=====================

.. cpp:struct:: OcaMediaSinkConnector
    
    Media sink (i.e. input) connector. Connects to an inbound stream. Collected by  **OcaMediaTransportNetwork** .

    .. cpp:member:: OcaMediaConnectorID IDInternal

        Internal ID.

    .. cpp:member:: OcaString IDExternal

        Public name of connector. May be published to the media transport network, depending on the type of network.

    .. cpp:member:: OcaMediaConnection Connection

        Descriptor of the stream connection to this connector. If there is no stream connected to this controller, (i.e. property Connected = FALSE), the value of this property is undefined.

    .. cpp:member:: OcaList<OcaMediaCoding> AvailableCodings

        List of codings available for this connector.

    .. cpp:member:: OcaUint16 PinCount

        Number of pins in this connector.

    .. cpp:member:: OcaMultiMap<OcaUint16, OcaPortID> ChannelPinMap

        Map of stream pins (sink channels) to OCA ports (output ports) of the owning  **OcaMediaNetwork** object. This defines what pins that are received from the network are sent to what OCA ports. A pin can only carry one network channel, but can be sent to multiple ports. That is why this data member is a multimap, a pin identifier can map to multiple ports. A pin is identified by an OcaUint16 with value 1..MaxPinCount. Not having a certain pin identifier in this map means that the pin is empty (i.e. not carrying a sink channel). A pin identifier cannot be part of the map more than MaxChannelsPerPin times, unless MaxChannelsPerPin is zero.

    .. cpp:member:: OcaDBFS AlignmentLevel

        Alignment level of the interface. Note that the dBFS value is referenced to the  *interface's* fullscale value, not to device's internal fullscale value.

    .. cpp:member:: OcaDB AlignmentGain

        Alignment gain for the connector. This value will be applied to all signals incoming through all pins.

    .. cpp:member:: OcaMediaCoding CurrentCoding

        Coding currently used by this connector.


OCP.1 Encoding
--------------

========================================== ==================================================== ==================================
Field                                      Basic type                                           Byte length                       
========================================== ==================================================== ==================================
IDInternal.Index                           OcaUint16                                            2                                 
IDExternal.Len                             OcaUint16                                            2                                 
IDExternal.Value                           string                                               variable                          
Connection.Secure                          OcaBoolean                                           1                                 
Connection.StreamParameters.Value.DataSize OcaUint16                                            2                                 
Connection.StreamParameters.Value.Data     OcaUint8                                             1 * Count                         
Connection.StreamCastMode                  OcaEnumItem                                          1                                 
Connection.StreamChannelCount              OcaUint16                                            2                                 
AvailableCodings                           OcaList<{OcaUint16, {OcaUint16, string}, OcaUint32}> (2 + Count * (6 + (2 + variable)))
PinCount                                   OcaUint16                                            2                                 
ChannelPinMap                              OcaMultiMap<OcaUint16, {OcaEnumItem, OcaUint16}>     (2 + 5 * Count)                   
AlignmentLevel.Value.Value                 OcaFloat32                                           4                                 
AlignmentGain.Value                        OcaFloat32                                           4                                 
CurrentCoding.CodingSchemeID.Value         OcaUint16                                            2                                 
CurrentCoding.CodecParameters.Len          OcaUint16                                            2                                 
CurrentCoding.CodecParameters.Value        string                                               variable                          
CurrentCoding.ClockONo.ONo                 OcaUint32                                            4                                 
========================================== ==================================================== ==================================


.. _OcaMediaSourceConnector:

OcaMediaSourceConnector
=======================

.. cpp:struct:: OcaMediaSourceConnector
    
    Media source (i.e. output) connector. Connects to an outbound stream. Collected by  **OcaMediaTransportNetwork** .

    .. cpp:member:: OcaMediaConnectorID IDInternal

        Internal ID.

    .. cpp:member:: OcaString IDExternal

        Public name of connector. May be published to the media transport network, depending on the type of network.

    .. cpp:member:: OcaMediaConnection Connection

        Descriptor of the stream connection to this connector. If there is no stream connected to this controller, (i.e. property Connected = FALSE), the value of this property is undefined.

    .. cpp:member:: OcaList<OcaMediaCoding> AvailableCodings

        List of codings available for this connector.

    .. cpp:member:: OcaUint16 PinCount

        Number of pins in this connector.

    .. cpp:member:: OcaMap<OcaUint16, OcaPortID> ChannelPinMap

        Map of stream pins (source channels) to OCA ports (input ports) of the owning  **OcaMediaNetwork** object. This defines what source channels are sent to the network. A pin is identified by an OcaUint16 with value 1..MaxPinCount. Not having a certain pin identifier in this map means that the pin is empty (i.e. not carrying a source channel).

    .. cpp:member:: OcaDBFS AlignmentLevel

        Alignment level of the interface. Note that the dBFS value is referenced to the  *interface's* fullscale value, not to device's internal fullscale value.

    .. cpp:member:: OcaMediaCoding CurrentCoding

        Coding currently used by this connector.


OCP.1 Encoding
--------------

========================================== ==================================================== ==================================
Field                                      Basic type                                           Byte length                       
========================================== ==================================================== ==================================
IDInternal.Index                           OcaUint16                                            2                                 
IDExternal.Len                             OcaUint16                                            2                                 
IDExternal.Value                           string                                               variable                          
Connection.Secure                          OcaBoolean                                           1                                 
Connection.StreamParameters.Value.DataSize OcaUint16                                            2                                 
Connection.StreamParameters.Value.Data     OcaUint8                                             1 * Count                         
Connection.StreamCastMode                  OcaEnumItem                                          1                                 
Connection.StreamChannelCount              OcaUint16                                            2                                 
AvailableCodings                           OcaList<{OcaUint16, {OcaUint16, string}, OcaUint32}> (2 + Count * (6 + (2 + variable)))
PinCount                                   OcaUint16                                            2                                 
ChannelPinMap                              OcaMap<OcaUint16, {OcaEnumItem, OcaUint16}>          (2 + 5 * Count)                   
AlignmentLevel.Value.Value                 OcaFloat32                                           4                                 
CurrentCoding.CodingSchemeID.Value         OcaUint16                                            2                                 
CurrentCoding.CodecParameters.Len          OcaUint16                                            2                                 
CurrentCoding.CodecParameters.Value        string                                               variable                          
CurrentCoding.ClockONo.ONo                 OcaUint32                                            4                                 
========================================== ==================================================== ==================================


.. _OcaMediaConnectorID:

OcaMediaConnectorID
===================

.. cpp:type:: OcaMediaConnectorID = OcaUint16

    Internal ID of media connector. Unique within its owner, which will be an OcaMediaTransportNetwork instance.
.. _OcaMediaConnectorStatus:

OcaMediaConnectorStatus
=======================

.. cpp:struct:: OcaMediaConnectorStatus
    
    Represents the current status of a media (source or sink) connector.

    .. cpp:member:: OcaMediaConnectorID ConnectorID

        ID of the connector for which this status is valid

    .. cpp:member:: OcaMediaConnectorState State

        Connector state

    .. cpp:member:: OcaUint16 ErrorCode

        Indicates what type of error the connector is in (only relevant if the State is Fault).


OCP.1 Encoding
--------------

================= =========== ===========
Field             Basic type  Byte length
================= =========== ===========
ConnectorID.Index OcaUint16   2          
State             OcaEnumItem 1          
ErrorCode         OcaUint16   2          
================= =========== ===========


.. _OcaMediaConnectorState:

OcaMediaConnectorState
======================

.. cpp:enum:: OcaMediaConnectorState : uint8_t

    Status options for a stream connector.

    .. cpp:enumerator:: Stopped = 0

        Connector has no media connection and no media data is being transferred.
    .. cpp:enumerator:: SettingUp = 1

        Stream connection is being set up. Media data is not flowing.
    .. cpp:enumerator:: Running = 2

        Media data is flowing since the connection is established.
    .. cpp:enumerator:: Paused = 3

        Media transfer is stopped. Existing connection is intact.
    .. cpp:enumerator:: Fault = 4

        Data transfer has been halted due to errors. Working storage has not been freed.
.. _OcaMediaConnectorCommand:

OcaMediaConnectorCommand
========================

.. cpp:enum:: OcaMediaConnectorCommand : uint8_t

    Command values for OcaMediaNetwork.ControlConnector(...)

    .. cpp:enumerator:: None = 0

        No-op. State is not changed.
    .. cpp:enumerator:: Start = 1

        Commence media data connection-making and data transfer. Resulting state = Running.
    .. cpp:enumerator:: Pause = 2

        Pause transferring media data, but preserve media connections. Resulting state = Paused.
.. _OcaMediaConnection:

OcaMediaConnection
==================

.. cpp:struct:: OcaMediaConnection
    
    A single-channel or multichannel connection between a local media connector (i.e.  **OcaMedia(Source/Sink)Connector** instance) of an  **OcaMediaTransportNetwork** object in this node and another ("remote") media source or sink. Normally, the remote source or sink is in another node. The remote end may or may not be an OCA-compliant device. A connection is unidirectional. Its direction is determined by the connector that owns the connection. Its direction is either:  
    
     -  *Outbound:* A signal flow from a  **source** connector to an external destination; or
     
    
     -  *Inbound:* A signal flow from an external source to a  **sink** connector.
      An  **OcaMediaConnection** object may represent a connection to either a unicast or a multicast stream. Any given  **OcaMedia(Source/Sink)Connector** object will only have one media connection. In non-OCA documents, connections are sometimes referred to as  *streams*  or  *flows.* 

    .. cpp:member:: OcaBoolean Secure

        True iff connection is secure.

    .. cpp:member:: OcaMediaStreamParameters StreamParameters

        Stream parameters (encoding, sampling, etc). Format is media network type dependent.

    .. cpp:member:: OcaMediaStreamCastMode StreamCastMode

        Unicast or multicast

    .. cpp:member:: OcaUint16 StreamChannelCount

        Number of channels in connected stream


OCP.1 Encoding
--------------

=============================== =========== ===========
Field                           Basic type  Byte length
=============================== =========== ===========
Secure                          OcaBoolean  1          
StreamParameters.Value.DataSize OcaUint16   2          
StreamParameters.Value.Data     OcaUint8    1 * Count  
StreamCastMode                  OcaEnumItem 1          
StreamChannelCount              OcaUint16   2          
=============================== =========== ===========


.. _OcaMediaStreamCastMode:

OcaMediaStreamCastMode
======================

.. cpp:enum:: OcaMediaStreamCastMode : uint8_t

    Type of media endpoint: unicast or multicast.

    .. cpp:enumerator:: None = 0

        Undefined streamcast mode
    .. cpp:enumerator:: Unicast = 1

        Unicast stream
    .. cpp:enumerator:: Multicast = 2

        Multicast stream
.. _OcaMediaStreamParameters:

OcaMediaStreamParameters
========================

.. cpp:type:: OcaMediaStreamParameters = OcaBlob

    Media stream parameters. Definition is media transport type dependent. Appropriate subclasses will be defined for specific X210 adaptations.
.. _OcaMediaCoding:

OcaMediaCoding
==============

.. cpp:struct:: OcaMediaCoding
    
    Codec ID + Coding parameters

    .. cpp:member:: OcaMediaCodingSchemeID CodingSchemeID

        ID of coding scheme to use.

    .. cpp:member:: OcaString CodecParameters

        Coding parameters. Content is coding-scheme-dependent.

    .. cpp:member:: OcaONo ClockONo

        Object number of OcaMediaClock3 object to use for this coding scheme. May be zero if no OcaMediaClock3 object is used.


OCP.1 Encoding
--------------

===================== ========== ===========
Field                 Basic type Byte length
===================== ========== ===========
CodingSchemeID.Value  OcaUint16  2          
CodecParameters.Len   OcaUint16  2          
CodecParameters.Value string     variable   
ClockONo.ONo          OcaUint32  4          
===================== ========== ===========


.. _OcaMediaCodingSchemeID:

OcaMediaCodingSchemeID
======================

.. cpp:type:: OcaMediaCodingSchemeID = OcaUint16

    Codec parameters
.. _OcaSDPString:

OcaSDPString
============

.. cpp:type:: OcaSDPString = OcaString

    Codec parameters