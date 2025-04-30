.. _ocalog:

1.5.1  OcaLog
=============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaDataset <ocadataset>` : :ref:`OcaLog <ocalog>`

.. cpp:class:: OcaLog: OcaDataset

    A log object. Child of **OcaDataSet.**

    **Properties**:


    .. _ocalog_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.5.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

        This property has id ``1.1``.

    .. _ocalog_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocalog_enabled:

    .. cpp:member:: OcaBoolean Enabled

        TRUE if and only if logging is enabled.

        This property has id ``3.1``.

    .. _ocalog_severitythreshold:

    .. cpp:member:: OcaLogSeverityLevel SeverityThreshold

        Log input filter: Only events whose severity level designator values are
        at or below this threshold will be logged. Note: **OcaLogSeverityLevel**
        is defined to follow the Syslog format as described in [RFC 5424]. In
        [RFC 5424], higher importance of an event is represented by a lower
        numeric value of its Severity Level.

        This property has id ``3.2``.

    Properties inherited from :ref:`ocadataset`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaDataset::ClassID <ocadataset_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaDataset::ClassVersion <ocadataset_classversion>`

    - :cpp:texpr:`OcaTime` :ref:`OcaDataset::LastModificationTime <ocadataset_lastmodificationtime>`

    - :cpp:texpr:`OcaUint64` :ref:`OcaDataset::MaxSize <ocadataset_maxsize>`

    - :cpp:texpr:`OcaString` :ref:`OcaDataset::Name <ocadataset_name>`

    - :cpp:texpr:`OcaONo` :ref:`OcaDataset::Owner <ocadataset_owner>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaDataset::ReadOnly <ocadataset_readonly>`

    - :cpp:texpr:`OcaMimeType` :ref:`OcaDataset::Type <ocadataset_type>`


    **Methods**:


    .. _ocalog_addlogrecord:

    .. cpp:function:: OcaStatus AddLogRecord(OcaLogRecord Entry)

        Adds a log entry.

        This method has id ``3.1``.

        - :cpp:expr:`Entry`: Input parameter.


    .. _ocalog_getseveritythreshold:

    .. cpp:function:: OcaStatus GetSeverityThreshold(OcaLogSeverityLevel &Severity)

        Gets the value of the **SeverityThreshold** property.

        This method has id ``3.2``.

        - :cpp:expr:`Severity`: Output parameter.


    .. _ocalog_setseveritythreshold:

    .. cpp:function:: OcaStatus SetSeverityThreshold(OcaLogSeverityLevel Severity)

        Sets the value of the **SeverityThreshold** property.

        This method has id ``3.3``.

        - :cpp:expr:`Severity`: Input parameter.


    .. _ocalog_openretrievalsession:

    .. cpp:function:: OcaStatus OpenRetrievalSession(OcaLockState LockType, OcaLogFilter Filter, OcaIOSessionHandle &Handle)

        Opens a log retrieval session. Sets the record filter that the
        retrievals will use. Returns a handle for subsequent
        **RetrieveRecords(...)** calls to use.

        This method has id ``3.4``.

        - :cpp:expr:`LockType`: Input parameter.


        - :cpp:expr:`Filter`: Input parameter.


        - :cpp:expr:`Handle`: Output parameter.


    .. _ocalog_closeretrievalsession:

    .. cpp:function:: OcaStatus CloseRetrievalSession(OcaIOSessionHandle Handle)

        Closes a log retrieval session.

        This method has id ``3.5``.

        - :cpp:expr:`Handle`: Input parameter.


    .. _ocalog_retrieverecords:

    .. cpp:function:: OcaStatus RetrieveRecords(OcaIOSessionHandle Handle, OcaUint64 RecStartNo, OcaUint16 RecCount, OcaUint64 MaxDataLength, OcaBoolean &EndOfData, OcaUint64 &LengthOfRequestedData, OcaList<OcaLogRecord> &Records)

        In a given log reading session, retrieves the next log record(s) that
        match the session's retrieval criteria. There must have an open log
        retrieval session created by calling OpenLogRetrievalSession(...). This
        call specifies the retrieval criteria. Returns **.EndOfData**=TRUE when
        there are no more records to retrieve.

        This method has id ``3.6``.

        - :cpp:expr:`Handle`: Input parameter.


        - :cpp:expr:`RecStartNo`: Input parameter.


        - :cpp:expr:`RecCount`: Input parameter.


        - :cpp:expr:`MaxDataLength`: Input parameter.


        - :cpp:expr:`EndOfData`: Output parameter.


        - :cpp:expr:`LengthOfRequestedData`: Output parameter.


        - :cpp:expr:`Records`: Output parameter.


    .. _ocalog_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &Enabled)

        Gets the value of the **Enabled** property.

        This method has id ``3.7``.

        - :cpp:expr:`Enabled`: Output parameter.


    .. _ocalog_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean Enabled)

        Sets the value of the **Enabled** property.

        This method has id ``3.8``.

        - :cpp:expr:`Enabled`: Input parameter.


    Methods inherited from :ref:`ocadataset`:

    - :ref:`OcaDataset::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaDataset::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaDataset::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaDataset::GetRole <ocaroot_getrole>`

    - :ref:`OcaDataset::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaDataset::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaDataset::Unlock <ocaroot_unlock>`

    - :ref:`OcaDataset::Clear <ocadataset_clear>`

    - :ref:`OcaDataset::Close <ocadataset_close>`

    - :ref:`OcaDataset::GetDatasetSizes <ocadataset_getdatasetsizes>`

    - :ref:`OcaDataset::GetLastModificationTime <ocadataset_getlastmodificationtime>`

    - :ref:`OcaDataset::GetName <ocadataset_getname>`

    - :ref:`OcaDataset::GetOwner <ocadataset_getowner>`

    - :ref:`OcaDataset::GetReadOnly <ocadataset_getreadonly>`

    - :ref:`OcaDataset::GetType <ocadataset_gettype>`

    - :ref:`OcaDataset::OpenRead <ocadataset_openread>`

    - :ref:`OcaDataset::OpenWrite <ocadataset_openwrite>`

    - :ref:`OcaDataset::Read <ocadataset_read>`

    - :ref:`OcaDataset::SetName <ocadataset_setname>`

    - :ref:`OcaDataset::SetReadOnly <ocadataset_setreadonly>`

    - :ref:`OcaDataset::SetType <ocadataset_settype>`

    - :ref:`OcaDataset::Write <ocadataset_write>`

