.. _ocamediatransportsessionagent:

1.2.20  OcaMediaTransportSessionAgent
=====================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaMediaTransportSessionAgent <ocamediatransportsessionagent>`

.. cpp:class:: OcaMediaTransportSessionAgent: OcaAgent

    Agent to set up, monitor, control, and take down media transport sessions.
    This shall be the base class for the AES70-CM4 connection management
    feature. See [AES70-1(Connection Management)]. This is an optional class.
    Session management functionality is not a mandatory for CM4 implementations.

    **Properties**:


    .. _ocamediatransportsessionagent_adaptationdata:

    .. cpp:member:: OcaAdaptationData AdaptationData

        Session-type-specific data.

        This property has id ``3.4``.

    .. _ocamediatransportsessionagent_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.20"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediatransportsessionagent_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamediatransportsessionagent_sessions:

    .. cpp:member:: OcaList<OcaMediaTransportSession> Sessions

        Set of transport sessions this Agent contains.

        This property has id ``3.2``.

    .. _ocamediatransportsessionagent_sessionstatuses:

    .. cpp:member:: OcaMap<OcaMediaTransportSessionID, OcaMediaTransportSessionStatus> SessionStatuses

        Statuses of transport sessions this Agent contains.

        This property has id ``3.3``.

    .. _ocamediatransportsessionagent_sessiontype:

    .. cpp:member:: const OcaString SessionType

        Type of session supported by this session agent. Read-only string value.
        Values beginning with"oca" in any character case are reserved.

        This property has id ``3.1``.

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


    .. _ocamediatransportsessionagent_getsessiontype:

    .. cpp:function:: OcaStatus GetSessionType(OcaString &Type)

        Gets type of session supported by this session agent.

        This method has id ``3.1``.

        - :cpp:expr:`Type`: Output parameter.


    .. _ocamediatransportsessionagent_getsessions:

    .. cpp:function:: OcaStatus GetSessions(OcaList<OcaMediaTransportSession> &Sessions)

        Gets the list of transport sessions held by this Agent.

        This method has id ``3.2``.

        - :cpp:expr:`Sessions`: Output parameter.


    .. _ocamediatransportsessionagent_getsession:

    .. cpp:function:: OcaStatus GetSession(OcaMediaTransportSessionID ID, OcaMediaTransportSession &Session)

        Gets the designated session.

        This method has id ``3.3``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Session`: Output parameter.


    .. _ocamediatransportsessionagent_addsession:

    .. cpp:function:: OcaStatus AddSession()

        Adds a new session. Returns given **OcaMediaTransportSession** parameter
        with session ID filled in.

        This method has id ``3.4``.

    .. _ocamediatransportsessionagent_configuresession:

    .. cpp:function:: OcaStatus ConfigureSession(OcaMediaTransportSessionID IDinternal, OcaBlob IDexternal, OcaString UserLabel, OcaBlob AdaptationData)

        Configures a session.

        This method has id ``3.5``.

        - :cpp:expr:`IDinternal`: Input parameter.


        - :cpp:expr:`IDexternal`: Input parameter.


        - :cpp:expr:`UserLabel`: Input parameter.


        - :cpp:expr:`AdaptationData`: Input parameter.


    .. _ocamediatransportsessionagent_deletesession:

    .. cpp:function:: OcaStatus DeleteSession(OcaMediaTransportSessionID ID)

        Deletes the designated session. Closes all connections the session
        contains.

        This method has id ``3.6``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportsessionagent_resetsession:

    .. cpp:function:: OcaStatus ResetSession(OcaMediaTransportSessionID ID)

        Resets the designated session. Returns the session to the state it has
        following a device reset.

        This method has id ``3.7``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportsessionagent_setstreamingenabled:

    .. cpp:function:: OcaStatus SetStreamingEnabled(OcaMediaTransportSessionID ID, OcaBoolean Active)

        Sets the streaming enabled switch.

        This method has id ``3.8``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Active`: Input parameter.


    .. _ocamediatransportsessionagent_startstreaming:

    .. cpp:function:: OcaStatus StartStreaming(OcaMediaTransportSessionID ID)

        if **StreamingEnabled** is TRUE, changes state from
        **ConnectedNotStreaming** to **ConnectedStreaming**.

        This method has id ``3.9``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportsessionagent_stopstreaming:

    .. cpp:function:: OcaStatus StopStreaming(OcaMediaTransportSessionID ID)

        if state is **ConnectedStreaming**, changes state to
        **ConnectedNotStreaming**.

        This method has id ``3.10``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportsessionagent_getsessionstatuses:

    .. cpp:function:: OcaStatus GetSessionStatuses(OcaMap<OcaMediaTransportSessionID, OcaMediaTransportSessionStatus> &Sessions)

        Gets the map of statuses of transport sessions held by this Agent.

        This method has id ``3.11``.

        - :cpp:expr:`Sessions`: Output parameter.


    .. _ocamediatransportsessionagent_getsessionstatus:

    .. cpp:function:: OcaStatus GetSessionStatus(OcaMediaTransportSessionID ID, OcaMediaTransportSessionStatus &Session)

        Gets status of the designated transport session.

        This method has id ``3.12``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Session`: Output parameter.


    .. _ocamediatransportsessionagent_addconnection:

    .. cpp:function:: OcaStatus AddConnection(OcaMediaTransportSessionID SessionID)

        Adds a new connection to an existing transport session. Returns given
        **OcaMediaTransportSessionConnection** parameter with connection ID
        filled in.

        This method has id ``3.13``.

        - :cpp:expr:`SessionID`: Input parameter.


    .. _ocamediatransportsessionagent_configureconnection:

    .. cpp:function:: OcaStatus ConfigureConnection(OcaMediaTransportSessionID SessionID, OcaMediaTransportSessionConnectionID ConnectionID, OcaMediaStreamEndpointID LocalEndpointID, OcaBlob RemoteEndpointID)

        Configures a connection.

        This method has id ``3.14``.

        - :cpp:expr:`SessionID`: Input parameter.


        - :cpp:expr:`ConnectionID`: Input parameter.


        - :cpp:expr:`LocalEndpointID`: Input parameter.


        - :cpp:expr:`RemoteEndpointID`: Input parameter.


    .. _ocamediatransportsessionagent_deleteconnection:

    .. cpp:function:: OcaStatus DeleteConnection(OcaMediaTransportSessionID SessionID, OcaMediaTransportSessionConnectionID ConnectionID)

        Deletes a connection from a transport session.

        This method has id ``3.15``.

        - :cpp:expr:`SessionID`: Input parameter.


        - :cpp:expr:`ConnectionID`: Input parameter.


    .. _ocamediatransportsessionagent_deleteconnections:

    .. cpp:function:: OcaStatus DeleteConnections(OcaMediaTransportSessionID SessionID)

        Deletes all connections from a transport session.

        This method has id ``3.16``.

        - :cpp:expr:`SessionID`: Input parameter.


    .. _ocamediatransportsessionagent_getadaptationdata:

    .. cpp:function:: OcaStatus GetAdaptationData(OcaAdaptationData &Data)

        Gets value of property **AdaptationData**

        This method has id ``3.17``.

        - :cpp:expr:`Data`: Output parameter.


    .. _ocamediatransportsessionagent_setadaptationdata:

    .. cpp:function:: OcaStatus SetAdaptationData(OcaAdaptationData Data)

        Sets value of property **AdaptationData**

        This method has id ``3.18``.

        - :cpp:expr:`Data`: Input parameter.


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

