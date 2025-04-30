.. _ocamediarecorderplayer:

1.1.7.1  OcaMediaRecorderPlayer
===============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaDatasetWorker <ocadatasetworker>` : :ref:`OcaMediaRecorderPlayer <ocamediarecorderplayer>`

.. cpp:class:: OcaMediaRecorderPlayer: OcaDatasetWorker

    Media volume recorder/player that shall provide streaming data access into
    and out of **OcaDataset** objects whose Datasets are media files.

    **Properties**:


    .. _ocamediarecorderplayer_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.7.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamediarecorderplayer_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamediarecorderplayer_playoption:

    .. cpp:member:: OcaMediaPlayOption PlayOption


         - Play to end of record/play window and leave Dataset open,

         - Play to end of record/play window, then close Dataset, or

         - Repeat record/play window until Stop() or Close() is called.



        This property has id ``4.4``.

    .. _ocamediarecorderplayer_state:

    .. cpp:member:: OcaMediaRecorderPlayerState State

        State of this object

        This property has id ``4.1``.

    .. _ocamediarecorderplayer_trackcount:

    .. cpp:member:: OcaUint16 TrackCount

        Number of tracks (signal channels) in the current media volume. Zero if
        no media volume is open.

        This property has id ``4.2``.

    .. _ocamediarecorderplayer_trackfunctions:

    .. cpp:member:: OcaList<OcaMediaTrackFunction> TrackFunctions

        List of track functions. Track function determines whether a track
        (signal channels) will play in a play and/or record operation, and/or
        record in a record operation.

        This property has id ``4.3``.

    .. _ocamediarecorderplayer_windowend:

    .. cpp:member:: OcaMediaVolumePosition WindowEnd

        Last position of current record/play window

        This property has id ``4.6``.

    .. _ocamediarecorderplayer_windowstart:

    .. cpp:member:: OcaMediaVolumePosition WindowStart

        First position of current record/play window

        This property has id ``4.5``.

    Properties inherited from :ref:`ocadatasetworker`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaMap<OcaPortID, OcaPortClockMapEntry>` :ref:`OcaWorker::PortClockMap <ocaworker_portclockmap>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaDatasetWorker::ClassID <ocadatasetworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaDatasetWorker::ClassVersion <ocadatasetworker_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaDatasetWorker::DatasetONo <ocadatasetworker_datasetono>`


    **Methods**:


    .. _ocamediarecorderplayer_open:

    .. cpp:function:: OcaStatus Open(OcaONo DatasetONo, OcaMediaAccessMode AccessMode, OcaLockState LockState)

        Opens a session with a media volume for playing or recording. Request a
        readonly or exclusive lock, if desired.

        This method has id ``4.1``.

        - :cpp:expr:`DatasetONo`: Input parameter.


        - :cpp:expr:`AccessMode`: Input parameter.


        - :cpp:expr:`LockState`: Input parameter.


    .. _ocamediarecorderplayer_close:

    .. cpp:function:: OcaStatus Close()

        Closes this object's session on the open media volume.

        This method has id ``4.2``.

    .. _ocamediarecorderplayer_record:

    .. cpp:function:: OcaStatus Record()

        Starts recording immediately. Overwrites the current record/play window,
        from current position to end.

        This method has id ``4.3``.

    .. _ocamediarecorderplayer_play:

    .. cpp:function:: OcaStatus Play()

        Starts playing immediately. Plays the current record/play window, from
        current position to end.

        This method has id ``4.4``.

    .. _ocamediarecorderplayer_stop:

    .. cpp:function:: OcaStatus Stop()

        Stops playing / recording immediately, does not close session. Leaves
        **Position** at (last accessed +1 ).

        This method has id ``4.5``.

    .. _ocamediarecorderplayer_reset:

    .. cpp:function:: OcaStatus Reset()

        Stops playing/recording immediately. Resets record/play window range to
        entire volume. Sets P**osition** to start of volume. Sets **PlayOption**
        to **Normal**. Does **not **reset track functions.

        This method has id ``4.6``.

    .. _ocamediarecorderplayer_getstate:

    .. cpp:function:: OcaStatus GetState(OcaMediaRecorderPlayerState &State)

        Returns current state of this **OcaMediaRecorderPlayer** object.

        This method has id ``4.7``.

        - :cpp:expr:`State`: Output parameter.


    .. _ocamediarecorderplayer_gettrackcount:

    .. cpp:function:: OcaStatus GetTrackCount(OcaUint16 &TrackCount)

        Returns track count of currently open media volume, or zero if no volume
        is open.

        This method has id ``4.8``.

        - :cpp:expr:`TrackCount`: Output parameter.


    .. _ocamediarecorderplayer_settrackcount:

    .. cpp:function:: OcaStatus SetTrackCount(OcaUint16 TrackCount)

        Sets track count of currently open media volume. Fails if media volume
        is not open in RECORD mode, or if no media volume is open.

        This method has id ``4.9``.

        - :cpp:expr:`TrackCount`: Input parameter.


    .. _ocamediarecorderplayer_gettrackfunctions:

    .. cpp:function:: OcaStatus GetTrackFunctions(OcaList<OcaMediaTrackFunction> &Functions)

        Returns the list of track functions.

        This method has id ``4.10``.

        - :cpp:expr:`Functions`: Output parameter.


    .. _ocamediarecorderplayer_settrackfunctions:

    .. cpp:function:: OcaStatus SetTrackFunctions(OcaList<OcaMediaTrackFunction> Functions)

        Sets the list of track functions. Fails if no media volume is open.

        This method has id ``4.11``.

        - :cpp:expr:`Functions`: Input parameter.


    .. _ocamediarecorderplayer_getplayoption:

    .. cpp:function:: OcaStatus GetPlayOption(OcaMediaPlayOption &Option)

        Returns value of **PlayOption** property.

        This method has id ``4.12``.

        - :cpp:expr:`Option`: Output parameter.


    .. _ocamediarecorderplayer_setplayoption:

    .. cpp:function:: OcaStatus SetPlayOption(OcaMediaPlayOption Option)

        Sets value of **PlayOption** property.

        This method has id ``4.13``.

        - :cpp:expr:`Option`: Input parameter.


    .. _ocamediarecorderplayer_getposition:

    .. cpp:function:: OcaStatus GetPosition(OcaMediaVolumePosition &Position)

        Returns current media position or null value if no media volume is open.
        Value is relative to the start of the current interval.

        This method has id ``4.14``.

        - :cpp:expr:`Position`: Output parameter.


    .. _ocamediarecorderplayer_setposition:

    .. cpp:function:: OcaStatus SetPosition(OcaMediaVolumePosition Position)

        Sets media position. Value is relative to the start of the current
        interval.

        This method has id ``4.15``.

        - :cpp:expr:`Position`: Input parameter.


    .. _ocamediarecorderplayer_getwindowrange:

    .. cpp:function:: OcaStatus GetWindowRange(OcaMediaVolumePosition &FirstPosition, OcaMediaVolumePosition &LastPosition)

        Returns start and end point positions of current record/play window.

        This method has id ``4.16``.

        - :cpp:expr:`FirstPosition`: Output parameter.


        - :cpp:expr:`LastPosition`: Output parameter.


    .. _ocamediarecorderplayer_setwindowrange:

    .. cpp:function:: OcaStatus SetWindowRange(OcaMediaVolumePosition FirstPosition, OcaMediaVolumePosition LastPosition)

        Sets start and end point positions of current record/play window.

        This method has id ``4.17``.

        - :cpp:expr:`FirstPosition`: Input parameter.


        - :cpp:expr:`LastPosition`: Input parameter.


    Methods inherited from :ref:`ocadatasetworker`:

    - :ref:`OcaDatasetWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaDatasetWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaDatasetWorker::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaDatasetWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaDatasetWorker::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaDatasetWorker::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaDatasetWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaDatasetWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaDatasetWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaDatasetWorker::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaDatasetWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaDatasetWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaDatasetWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaDatasetWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaDatasetWorker::GetPath <ocaworker_getpath>`

    - :ref:`OcaDatasetWorker::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaDatasetWorker::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaDatasetWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaDatasetWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaDatasetWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaDatasetWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaDatasetWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaDatasetWorker::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaDatasetWorker::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaDatasetWorker::SetPortName <ocaworker_setportname>`

    - :ref:`OcaDatasetWorker::GetDatasetONo <ocadatasetworker_getdatasetono>`

