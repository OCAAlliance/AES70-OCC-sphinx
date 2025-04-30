.. _ocamediatransportapplication:

1.7.1  OcaMediaTransportApplication
===================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaNetworkApplication <ocanetworkapplication>` : :ref:`OcaMediaTransportApplication <ocamediatransportapplication>`

.. cpp:class:: OcaMediaTransportApplication: OcaNetworkApplication

    Connection Management 4 (CM4) class. Specifies the device's control
    interface to media transport functions. This is the anchoring class for CM4
    data structures. Abstract class that shall be subclassed for each media
    transport Adaptation.

    **Properties**:


    .. _ocamediatransportapplication_alignmentlevellimits:

    .. cpp:member:: OcaInterval<OcaDBFS> AlignmentLevelLimits

        Alignment level limits for newly-created **OcaMediaStreamEndpoint**
        instances. The min and max values of this property define respectively
        the lowest and highest alignment level values that may be specified when
        adding stream endpoints to this media transport application.

        This property has id ``3.9``.

    .. _ocamediatransportapplication_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.7.1"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediatransportapplication_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        This property is an override of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamediatransportapplication_endpoints:

    .. cpp:member:: OcaList<OcaMediaStreamEndpoint> Endpoints

        The list of stream endpoints this media transport application has.

        This property has id ``3.10``.

    .. _ocamediatransportapplication_endpointstatuses:

    .. cpp:member:: OcaMap<OcaMediaStreamEndpointID, OcaMediaStreamEndpointStatus> EndpointStatuses

        Map of states of this media transport application's endpoints. Map key
        is endpoint ID.

        This property has id ``3.11``.

    .. _ocamediatransportapplication_maxchannelsperendpoint:

    .. cpp:member:: OcaUint16 MaxChannelsPerEndpoint

        The maximum number of channels in a stream endpoint that this media
        transport application will support.

        This property has id ``3.6``.

    .. _ocamediatransportapplication_maxinputendpoints:

    .. cpp:member:: OcaUint16 MaxInputEndpoints

        The maximum number of input stream endpoints this media transport
        network application can have (read-only property).

        This property has id ``3.3``.

    .. _ocamediatransportapplication_maxoutputendpoints:

    .. cpp:member:: OcaUint16 MaxOutputEndpoints

        The maximum number of output stream endpoints this media transport
        application can have (read-only property).

        This property has id ``3.4``.

    .. _ocamediatransportapplication_maxportsperchannel:

    .. cpp:member:: OcaUint16 MaxPortsPerChannel

        The maximum number of ports per stream endpoint channel that this media
        transport application will support. Value of zero indicates there is no
        specific limit.

        This property has id ``3.5``.

    .. _ocamediatransportapplication_mediastreammodecapabilities:

    .. cpp:member:: OcaList<OcaMediaStreamModeCapability> MediaStreamModeCapabilities

        List of media stream mode capability descriptors that apply to this
        media transport application.

        This property has id ``3.7``.

    .. _ocamediatransportapplication_portclockmap:

    .. cpp:member:: OcaMap<OcaPortID, OcaPortClockMapEntry> PortClockMap

        Map that connects **OcaMediaClock3** object numbers to this network's
        input and output **OcaPorts** and specifies sampling rate converters, if
        any. **OcaPortID** = {mode,index}, where mode = Input or Output.
        Optional property.

        This property has id ``3.2``.

    .. _ocamediatransportapplication_ports:

    .. cpp:member:: OcaList<OcaPort> Ports

        The list of **OcaPorts** this network offers on its inward face.

        This property has id ``3.1``.

    .. _ocamediatransportapplication_transportsessioncontrolagentonos:

    .. cpp:member:: OcaList<OcaONo> TransportSessionControlAgentONos

        Object number(s) of media transport session control agent(s) associated
        with this media transport application.

        This property has id ``3.13``.

    .. _ocamediatransportapplication_transporttimingparameters:

    .. cpp:member:: OcaMediaTransportTimingParameters TransportTimingParameters

        Timing parameters for media transport through this media transport
        application.

        This property has id ``3.8``.

    Properties inherited from :ref:`ocanetworkapplication`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaAdaptationData` :ref:`OcaNetworkApplication::AdaptationData <ocanetworkapplication_adaptationdata>`

    - :cpp:texpr:`OcaAdaptationIdentifier` :ref:`OcaNetworkApplication::AdaptationIdentifier <ocanetworkapplication_adaptationidentifier>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaNetworkApplication::ClassID <ocanetworkapplication_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaNetworkApplication::ClassVersion <ocanetworkapplication_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaNetworkApplication::Label <ocanetworkapplication_label>`

    - :cpp:texpr:`OcaList<OcaNetworkInterfaceAssignment>` :ref:`OcaNetworkApplication::NetworkInterfaceAssignments <ocanetworkapplication_networkinterfaceassignments>`

    - :cpp:texpr:`OcaONo` :ref:`OcaNetworkApplication::Owner <ocanetworkapplication_owner>`


    **Methods**:


    .. _ocamediatransportapplication_addport:

    .. cpp:function:: OcaStatus AddPort(OcaString Name, OcaIODirection Mode, OcaPortID &ID)

        Adds an input or output port..

        This method has id ``3.1``.

        - :cpp:expr:`Name`: Input parameter.


        - :cpp:expr:`Mode`: Input parameter.


        - :cpp:expr:`ID`: Output parameter.


    .. _ocamediatransportapplication_deleteport:

    .. cpp:function:: OcaStatus DeletePort(OcaPortID ID)

        Deletes an input or output port..

        This method has id ``3.2``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportapplication_getports:

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        Gets the list of ports owned by this object.

        This method has id ``3.3``.

        - :cpp:expr:`OcaPorts`: Output parameter.


    .. _ocamediatransportapplication_getportname:

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        Gets the name of the designated port.

        This method has id ``3.4``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Name`: Output parameter.


    .. _ocamediatransportapplication_setportname:

    .. cpp:function:: OcaStatus SetPortName(OcaPortID PortID, OcaString Name)

        Sets the name of the designated port.

        This method has id ``3.5``.

        - :cpp:expr:`PortID`: Input parameter.


        - :cpp:expr:`Name`: Input parameter.


    .. _ocamediatransportapplication_getportclockmap:

    .. cpp:function:: OcaStatus GetPortClockMap(OcaMap<OcaPortID, OcaPortClockMapEntry> &Map)

        Gets the value of the **PortClockMap** property.

        This method has id ``3.6``.

        - :cpp:expr:`Map`: Output parameter.


    .. _ocamediatransportapplication_setportclockmap:

    .. cpp:function:: OcaStatus SetPortClockMap(OcaMap<OcaPortID, OcaPortClockMapEntry> Map)

        Sets the value of the **PortClockMap** property.

        This method has id ``3.7``.

        - :cpp:expr:`Map`: Input parameter.


    .. _ocamediatransportapplication_setportclockmapentry:

    .. cpp:function:: OcaStatus SetPortClockMapEntry(OcaPortID ID, OcaPortClockMapEntry Entry)

        Adds or replaces an entry in the **PortClockMap** property.

        This method has id ``3.8``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Entry`: Input parameter.


    .. _ocamediatransportapplication_deleteportclockmapentry:

    .. cpp:function:: OcaStatus DeletePortClockMapEntry(OcaPortID ID)

        Deletes the **PortClockMap** entry identified by the given ID.

        This method has id ``3.9``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportapplication_getportclockmapentry:

    .. cpp:function:: OcaStatus GetPortClockMapEntry(OcaPortID ID, OcaPortClockMapEntry &Entry)

        Retrieves the value of the **PortClockMap** entry identified by the
        given port ID.

        This method has id ``3.10``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Entry`: Output parameter.


    .. _ocamediatransportapplication_getmaxendpointcounts:

    .. cpp:function:: OcaStatus GetMaxEndpointCounts(OcaUint16 &MaxOutputCount, OcaUint16 &MaxInputCount)

        Gets the maximum number of input and output stream endpoints this media
        transport application supports.

        This method has id ``3.11``.

        - :cpp:expr:`MaxOutputCount`: Output parameter.


        - :cpp:expr:`MaxInputCount`: Output parameter.


    .. _ocamediatransportapplication_getmaxportsperchannel:

    .. cpp:function:: OcaStatus GetMaxPortsPerChannel(OcaUint16 &Value)

        Gets the maximum number of ports per stream endpoint channel this media
        transport application supports.

        This method has id ``3.12``.

        - :cpp:expr:`Value`: Output parameter.


    .. _ocamediatransportapplication_getmaxchannelsperendpoint:

    .. cpp:function:: OcaStatus GetMaxChannelsPerEndpoint(OcaUint16 &Value)

        Gets the maximum number of channels per stream endpoint this media
        transport application supports.

        This method has id ``3.13``.

        - :cpp:expr:`Value`: Output parameter.


    .. _ocamediatransportapplication_setalignmentlevellimits:

    .. cpp:function:: OcaStatus SetAlignmentLevelLimits(OcaInterval<OcaDBFS> Limits)

        Sets the alignment level limits for stream endpoints attached to this
        media transport application.

        This method has id ``3.14``.

        - :cpp:expr:`Limits`: Input parameter.


    .. _ocamediatransportapplication_getmediastreammodecapabilities:

    .. cpp:function:: OcaStatus GetMediaStreamModeCapabilities(OcaList<OcaMediaStreamModeCapability> &Capabilities)

        Gets this media transport application's media stream mode capability
        descriptors.

        This method has id ``3.15``.

        - :cpp:expr:`Capabilities`: Output parameter.


    .. _ocamediatransportapplication_setmediastreammodecapabilities:

    .. cpp:function:: OcaStatus SetMediaStreamModeCapabilities(OcaList<OcaMediaStreamModeCapability> Capabilities)

        Sets this media transport application's media stream mode capability
        descriptors. May only be called when there are no media stream endpoints
        defined. If this condition is not met, the call will return status value
        **InvalidRequest.**

        This method has id ``3.16``.

        - :cpp:expr:`Capabilities`: Input parameter.


    .. _ocamediatransportapplication_getmediastreammodecapability:

    .. cpp:function:: OcaStatus GetMediaStreamModeCapability(OcaID16 CapabilityID, OcaMediaStreamModeCapability &Capability)

        Gets a specific media stream mode capability descriptor.

        This method has id ``3.17``.

        - :cpp:expr:`CapabilityID`: Input parameter.


        - :cpp:expr:`Capability`: Output parameter.


    .. _ocamediatransportapplication_gettransporttimingparameters:

    .. cpp:function:: OcaStatus GetTransportTimingParameters(OcaMediaTransportTimingParameters &Parameters)

        Gets this media transport application's media transport timing
        parameters.

        This method has id ``3.18``.

        - :cpp:expr:`Parameters`: Output parameter.


    .. _ocamediatransportapplication_settransporttimingparameters:

    .. cpp:function:: OcaStatus SetTransportTimingParameters(OcaMediaTransportTimingParameters Parameters)

        Sets this media transport application's media transport timing
        parameters. Optional method.

        This method has id ``3.19``.

        - :cpp:expr:`Parameters`: Input parameter.


    .. _ocamediatransportapplication_getalignmentlevellimits:

    .. cpp:function:: OcaStatus GetAlignmentLevelLimits(OcaInterval<OcaDBFS> &Limits)

        Gets the min and max alignment levels for stream endpoints attached to
        this media transport application.

        This method has id ``3.20``.

        - :cpp:expr:`Limits`: Output parameter.


    .. _ocamediatransportapplication_getendpoints:

    .. cpp:function:: OcaStatus GetEndpoints(OcaList<OcaMediaStreamEndpoint> &Endpoints)

        Gets the descriptors of all the stream endpoints owned by this media
        transport application object.

        This method has id ``3.21``.

        - :cpp:expr:`Endpoints`: Output parameter.


    .. _ocamediatransportapplication_getendpoint:

    .. cpp:function:: OcaStatus GetEndpoint(OcaMediaStreamEndpointID ID, OcaMediaStreamEndpoint &Endpoint)

        Retrieves the descriptor of a given stream endpoint.

        This method has id ``3.22``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Endpoint`: Output parameter.


    .. _ocamediatransportapplication_getendpointstatuses:

    .. cpp:function:: OcaStatus GetEndpointStatuses(OcaMap<OcaMediaStreamEndpointID, OcaMediaStreamEndpointStatus> &Statuses)

        Gets the status of all the stream endpoints collected by this media
        transport application. Key of returned map is endpoint ID.

        This method has id ``3.23``.

        - :cpp:expr:`Statuses`: Output parameter.


    .. _ocamediatransportapplication_getendpointstatus:

    .. cpp:function:: OcaStatus GetEndpointStatus(OcaMediaStreamEndpointID ID, OcaMediaStreamEndpointStatus &Status)

        Gets the status of a single stream endpoint.

        This method has id ``3.24``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`Status`: Output parameter.


    .. _ocamediatransportapplication_addendpoint:

    .. cpp:function:: OcaStatus AddEndpoint(OcaMediaStreamEndpointState InitialStatus)

        Adds an Endpoint to this media transport application object. Parameters
        of the new Endpoint shall be given in the **Endpoint** parameter; Device
        shall return the same parameter with the new Endpoint ID filled in. The
        new Endpoint's **AlignmentLevel** value shall be within the bounds set
        by the property **AlignmentLevelLimits**.

        This method has id ``3.25``.

        - :cpp:expr:`InitialStatus`: Input parameter.


    .. _ocamediatransportapplication_deleteendpoint:

    .. cpp:function:: OcaStatus DeleteEndpoint(OcaMediaStreamEndpointID ID)

        Deletes a stream endpoint from this media transport application object.

        This method has id ``3.26``.

        - :cpp:expr:`ID`: Input parameter.


    .. _ocamediatransportapplication_applyendpointcommand:

    .. cpp:function:: OcaStatus ApplyEndpointCommand(OcaMediaStreamEndpointID EndpointID, OcaMediaStreamEndpointCommand Command)

        Changes the state of a given Endpoint.

        This method has id ``3.27``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`Command`: Input parameter.


    .. _ocamediatransportapplication_setendpointuserlabel:

    .. cpp:function:: OcaStatus SetEndpointUserLabel(OcaMediaStreamEndpointID EndpointID, OcaString Label)

        Sets the **UserLabel** field of the of the referenced Endpoint.

        This method has id ``3.28``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`Label`: Input parameter.


    .. _ocamediatransportapplication_setendpointmediastreammode:

    .. cpp:function:: OcaStatus SetEndpointMediaStreamMode(OcaMediaStreamEndpointID EndpointID, OcaMediaStreamMode StreamMode)

        Sets the **CurrentStreamMode** field of the of the designated stream
        endpoint.

        This method has id ``3.29``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`StreamMode`: Input parameter.


    .. _ocamediatransportapplication_setendpointchannelmap:

    .. cpp:function:: OcaStatus SetEndpointChannelMap(OcaMediaStreamEndpointID EndpointID, OcaMultiMap<OcaID16, OcaPortID> ChannelMap)

        Sets an Endpoint's ChannelMap field. Mapping rules:

         - Input Endpoint maps shall specify only OCA Output Ports.

         - Output Endpoint maps shall specify only OCA Input Ports.

         - Input Endpoint maps may specify any number of OCA Output Ports per
           stream channel.

         - Output Endpoint maps may specify at most one OCA Input Port per
           stream channel.



        This method has id ``3.30``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`ChannelMap`: Input parameter.


    .. _ocamediatransportapplication_setendpointalignmentlevel:

    .. cpp:function:: OcaStatus SetEndpointAlignmentLevel(OcaMediaStreamEndpointID EndpointID, OcaDBFS Level)

        Sets **OcaEndpoint.AlignmentLevel** for the identified endpoint.

        This method has id ``3.31``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`Level`: Input parameter.


    .. _ocamediatransportapplication_getendpointtimesource:

    .. cpp:function:: OcaStatus GetEndpointTimeSource(OcaMediaStreamEndpointID ID, OcaTimeReferenceType &ReferenceType, OcaString &ReferenceID)

        Gets type and ID of this Endpoint's time source.

        This method has id ``3.32``.

        - :cpp:expr:`ID`: Input parameter.


        - :cpp:expr:`ReferenceType`: Output parameter.


        - :cpp:expr:`ReferenceID`: Output parameter.


    .. _ocamediatransportapplication_setendpointadaptationdata:

    .. cpp:function:: OcaStatus SetEndpointAdaptationData(OcaMediaStreamEndpointID EndpointID, OcaAdaptationData Data)

        Sets the AdaptationData field of the given Endpoint.

        This method has id ``3.33``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`Data`: Input parameter.


    .. _ocamediatransportapplication_getendpointcountersets:

    .. cpp:function:: OcaStatus GetEndpointCounterSets(OcaMap<OcaMediaStreamEndpointID, OcaCounterSet> &Sets)

        Retrieves map of counter sets of all Endpoints.

        This method has id ``3.34``.

        - :cpp:expr:`Sets`: Output parameter.


    .. _ocamediatransportapplication_getendpointcounterset:

    .. cpp:function:: OcaStatus GetEndpointCounterSet(OcaMediaStreamEndpointID EndpointID, OcaCounterSet &CounterSet)

        Gets the Counterset of a designated Endpoint.

        This method has id ``3.35``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`CounterSet`: Output parameter.


    .. _ocamediatransportapplication_getendpointcounter:

    .. cpp:function:: OcaStatus GetEndpointCounter(OcaMediaStreamEndpointID EndpointID, OcaID16 CounterID, OcaCounter &Counter)

        Retrieves a Counter of a designated Endpoint

        This method has id ``3.36``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`Counter`: Output parameter.


    .. _ocamediatransportapplication_attachendpointcounternotifier:

    .. cpp:function:: OcaStatus AttachEndpointCounterNotifier(OcaMediaStreamEndpointID EndpointID, OcaID16 CounterID, OcaONo NotifierONo)

        Adds a Notifier to the designated Counter.

        This method has id ``3.37``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`NotifierONo`: Input parameter.


    .. _ocamediatransportapplication_detachendpointcounternotifier:

    .. cpp:function:: OcaStatus DetachEndpointCounterNotifier(OcaMediaStreamEndpointID EndpointID, OcaID16 CounterID, OcaONo NotifierONo)

        Removes a Notifier from the designated Counter.

        This method has id ``3.38``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`CounterID`: Input parameter.


        - :cpp:expr:`NotifierONo`: Input parameter.


    .. _ocamediatransportapplication_resetendpointcounterset:

    .. cpp:function:: OcaStatus ResetEndpointCounterSet(OcaMediaStreamEndpointID EndpointID, OcaID16 CounterID)

        Resets Counter(s) of one or all of this media transport application
        object's Endpoints.

         - If given Counter ID is zero, resets entire Counterset; otherwise,
           resets designated Counter only.

         - If given Endpoint ID is zero, resets the designated Counter(s) in all
           this media transport application object's Endpoints; otherwise,
           resets the designated Counter(s) in the designated Endpoint only.


        Resetting a Counter causes its value to be set to its initial value, as
        defined in its **OcaCounter** instance.

        This method has id ``3.39``.

        - :cpp:expr:`EndpointID`: Input parameter.


        - :cpp:expr:`CounterID`: Input parameter.


    .. _ocamediatransportapplication_gettransportsessioncontrolagentonos:

    .. cpp:function:: OcaStatus GetTransportSessionControlAgentONos(OcaList<OcaONo> &ONos)

        Gets list of ONos of Media Transport Session Agents associated with this
        media transport application object, or empty list if there aren't any.

        This method has id ``3.40``.

        - :cpp:expr:`ONos`: Output parameter.


    .. _ocamediatransportapplication_settransportsessioncontrolagentonos:

    .. cpp:function:: OcaStatus SetTransportSessionControlAgentONos(OcaList<OcaONo> ONos)

        Sets list of ONos of Media Transport Session Agents associated with this
        media transport application object. Optional method, mainly useful for
        dynamic devices.

        This method has id ``3.41``.

        - :cpp:expr:`ONos`: Input parameter.


    Methods inherited from :ref:`ocanetworkapplication`:

    - :ref:`OcaNetworkApplication::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaNetworkApplication::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaNetworkApplication::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaNetworkApplication::GetRole <ocaroot_getrole>`

    - :ref:`OcaNetworkApplication::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaNetworkApplication::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaNetworkApplication::Unlock <ocaroot_unlock>`

    - :ref:`OcaNetworkApplication::AttachCounterNotifier <ocanetworkapplication_attachcounternotifier>`

    - :ref:`OcaNetworkApplication::DetachCounterNotifier <ocanetworkapplication_detachcounternotifier>`

    - :ref:`OcaNetworkApplication::GetAdaptationData <ocanetworkapplication_getadaptationdata>`

    - :ref:`OcaNetworkApplication::GetAdaptationIdentifier <ocanetworkapplication_getadaptationidentifier>`

    - :ref:`OcaNetworkApplication::GetCounter <ocanetworkapplication_getcounter>`

    - :ref:`OcaNetworkApplication::GetCounterSet <ocanetworkapplication_getcounterset>`

    - :ref:`OcaNetworkApplication::GetLabel <ocanetworkapplication_getlabel>`

    - :ref:`OcaNetworkApplication::GetNetworkInterfaceAssignments <ocanetworkapplication_getnetworkinterfaceassignments>`

    - :ref:`OcaNetworkApplication::GetOwner <ocanetworkapplication_getowner>`

    - :ref:`OcaNetworkApplication::GetPath <ocanetworkapplication_getpath>`

    - :ref:`OcaNetworkApplication::ResetCounters <ocanetworkapplication_resetcounters>`

    - :ref:`OcaNetworkApplication::SetAdaptationData <ocanetworkapplication_setadaptationdata>`

    - :ref:`OcaNetworkApplication::SetLabel <ocanetworkapplication_setlabel>`

    - :ref:`OcaNetworkApplication::SetNetworkInterfaceAssignments <ocanetworkapplication_setnetworkinterfaceassignments>`

