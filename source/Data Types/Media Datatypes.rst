***************
Media Datatypes
***************

.. _OcaMediaPlayOption:

OcaMediaPlayOption
==================

.. cpp:enum:: OcaMediaPlayOption : uint8_t

    Options for media playback

    .. cpp:enumerator:: Normal = 0

        Play until end of specified interval is reached or operation is halted
        by a controller action.

    .. cpp:enumerator:: Autoclose = 1

        Play until end of specified interval is reached or operation is halted
        by a controller action. If end of interval is reached, close session.

    .. cpp:enumerator:: RepeatInterval = 2

        Repeat playback of specified interval until operation is halted by a
        controller action.

.. _OcaMediaRecorderPlayerState:

OcaMediaRecorderPlayerState
===========================

.. cpp:enum:: OcaMediaRecorderPlayerState : uint8_t

    State of **OcaMediaRecorderPlayer** object

    .. cpp:enumerator:: Idle = 0

        No media volume is open. Recorder/player is doing nothing.

    .. cpp:enumerator:: Stopped = 1

        Media volume is open but recorder/player is neither seeking, recording,
        nor playing.

    .. cpp:enumerator:: Seeking = 2

        Recorder/player is locating a designated position in a media file.

    .. cpp:enumerator:: Recording = 3

        Recorder/player is recording.

    .. cpp:enumerator:: Playing = 4

        Recorder/player is playing.

.. _OcaMediaAccessMode:

OcaMediaAccessMode
==================

.. cpp:enum:: OcaMediaAccessMode : uint8_t

    Media volume access mode: record or play.

    .. cpp:enumerator:: None = 0

        No media volume is open.

    .. cpp:enumerator:: Play = 1

        Media volume will be played.

    .. cpp:enumerator:: Record = 2

        Media volume will be recorded.

.. _OcaMediaTrackFunction:

OcaMediaTrackFunction
=====================

.. cpp:type:: OcaMediaTrackFunction = OcaBitSet16

    Media track function. Controls handling of a track during
    **OcaMediaRecorderPlayer** operations.

.. _OcaMediaVolumePositionType:

OcaMediaVolumePositionType
==========================

.. cpp:enum:: OcaMediaVolumePositionType : uint16_t

    Type of media position specified: samples or nanoseconds

    .. cpp:enumerator:: Samples = 0

        Position is specified as number of samples after start of this media
        volume.

    .. cpp:enumerator:: Seconds = 1

        Position is specified as time in floating-point seconds after start of
        this media volume.

.. _OcaMediaVolumePosition:

OcaMediaVolumePosition
======================

.. cpp:struct:: OcaMediaVolumePosition

    Position within a media volume - samples or seconds.

    .. cpp:member:: OcaMediaVolumePositionType PositionType

        What kind of position specification - samples or seconds.

    .. cpp:member:: OcaUint64 Position

        Position - sample count or time in floating-point seconds after start of
        Media Volume.

