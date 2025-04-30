*********************************
Media Transport Session Datatypes
*********************************

.. _OcaMediaTransportSessionID:

OcaMediaTransportSessionID
==========================

.. cpp:type:: OcaMediaTransportSessionID = OcaUint32

    Internal ID of a Media Transport Session

.. _OcaMediaTransportSessionConnectionID:

OcaMediaTransportSessionConnectionID
====================================

.. cpp:type:: OcaMediaTransportSessionConnectionID = OcaUint32

    Internal ID of a connection that belongs to a Media Transport Session

.. _OcaMediaTransportSession:

OcaMediaTransportSession
========================

.. cpp:struct:: OcaMediaTransportSession

    Container of all the Media Transport Sessions belonging to a Media Transport
    Session control Agent.

    .. cpp:member:: OcaMediaTransportSessionID IDInternal

        Internal ID, unique within OcaTransportSessionControlAgent instance.

    .. cpp:member:: OcaBlob IDExternal

        External ID, i.e. the ID that is published to the network. Format is
        Adaptation-specific.

    .. cpp:member:: OcaString UserLabel

        Arbitrary text label - not programmatically significant.

    .. cpp:member:: OcaBoolean StreamingEnabled

        TRUE if and only if media streaming is allowed. If set to FALSE, does
        not cause disconnection.

    .. cpp:member:: OcaAdaptationData AdaptationData

        Adaptation-specific data.

    .. cpp:member:: OcaList<OcaMediaTransportSessionConnection> Connections

        This session's stream connections.

    .. cpp:member:: OcaMap<OcaMediaTransportSessionConnectionID, OcaMediaTransportSessionConnectionState> ConnectionStates

        State(s) of session's connection(s). Map key is connection ID.

.. _OcaMediaTransportSessionConnection:

OcaMediaTransportSessionConnection
==================================

.. cpp:struct:: OcaMediaTransportSessionConnection

    A Media Stream connection belonging to an **OcaMediaTransportSession**
    instance.

    .. cpp:member:: OcaMediaTransportSessionConnectionID ID

        Local ID of this connection, unique within OcaMediaTransportSession
        instance.

    .. cpp:member:: OcaMediaStreamEndpointID LocalEndpointID

        Value of the **IDInternal** property of the **OcaMediaStreamEndpoint**
        descriptor that applies to the local endpoint of the connection.

    .. cpp:member:: OcaBlob RemoteEndpointID

        External ID of the remote endpoint of the connection. Typically, this
        will be the value of the **IDexternal** property of the applicable
        **OcaMediaStreamEndpoint** descriptor in the remote device.

.. _OcaMediaTransportSessionConnectionState:

OcaMediaTransportSessionConnectionState
=======================================

.. cpp:struct:: OcaMediaTransportSessionConnectionState

    State of a stream connection belonging to an **OcaMediaTransportSession**
    instance. The state of a stream connection is the union of the states of its
    two endpoints.

    .. cpp:member:: OcaMediaStreamEndpointState LocalEndpointState

        State of local endpoint of a connection.

    .. cpp:member:: OcaMediaStreamEndpointState RemoteEndpointState

        State of remote endpoint of a connection.

.. _OcaMediaTransportSessionStatus:

OcaMediaTransportSessionStatus
==============================

.. cpp:struct:: OcaMediaTransportSessionStatus

    Status of a media transport session. Two parts: a generic part, and an
    application-specific part.

    .. cpp:member:: OcaMediaTransportSessionState State

        Generic state of session

    .. cpp:member:: OcaBlob AdaptationData

        Adaptation-dependent state data

.. _OcaMediaTransportSessionState:

OcaMediaTransportSessionState
=============================

.. cpp:enum:: OcaMediaTransportSessionState : uint8_t

    State of a session

    .. cpp:enumerator:: Unconfigured = 1

        Session has no connection information

    .. cpp:enumerator:: Configured = 2

        Session has connection information but not all of its connections are
        actually connected.

    .. cpp:enumerator:: ConnectedNotStreaming = 3

        All Media Stream connections are connected but no data is flowing.

    .. cpp:enumerator:: ConnectedStreaming = 4

        All Media Stream connections are connected and data is flowing.

    .. cpp:enumerator:: Error = 5

        An error has occurred. Condition of Media Stream data flow is
        application- and circumstance-dependent.

