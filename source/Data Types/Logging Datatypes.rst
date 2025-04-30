*****************
Logging Datatypes
*****************

.. _OcaLogRecord:

OcaLogRecord
============

.. cpp:struct:: OcaLogRecord

    Format of a log record. Payload format is application-specific; header data
    is standard.

    .. cpp:member:: OcaUint32 FunctionalCategory

        Application-specific value used for categorizing log records for
        selective retrieval.

    .. cpp:member:: OcaLogSeverityLevel Severity

        Severity of log record. Recommended values are the same as those for the
        Syslog format as specified by [RFC 5424]; see also {Wiki-004}.

    .. cpp:member:: OcaONo EmitterONo

        ONo of object that generated the log record.

    .. cpp:member:: OcaTime Timestamp

        Date/time the log record was generated.

    .. cpp:member:: OcaBlob Payload

        Device- or application- specific content of the log record.

.. _OcaLogFilter:

OcaLogFilter
============

.. cpp:struct:: OcaLogFilter

    Filter for log entry retrieval.

    .. cpp:member:: OcaUint32 FunctionalCategory

        Application-specific value used for categorizing log records

    .. cpp:member:: OcaInterval<OcaLogSeverityLevel> SeverityRange

        Range of severity levels to retrieve

    .. cpp:member:: OcaONo EmitterONo

        ONo of object that generated the log record, or zero to accept log
        entries from all objects.

    .. cpp:member:: OcaInterval<OcaTime> TimestampRange

        Range of timestamps to be accepted.

.. _OcaLogSeverityLevel:

OcaLogSeverityLevel
===================

.. cpp:type:: OcaLogSeverityLevel = OcaInt32

    Severity of log entry. Negative values are reserved. Applications should use
    the same values as the severity header field in the Syslog format as
    specified by [RFC 5424].

