*************************
Media Connector Datatypes
*************************

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