.. _ocadataset:

1.5  OcaDataset
===============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaDataset <ocadataset>`

.. cpp:class:: OcaDataset: OcaRoot


     - An OCA Dataset. A dataset is like a simple binary file that can be read
       and written.

     - Every dataset is a separate **OcaDataset** object.



    **Properties**:


    .. _ocadataset_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.5"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property will be
        overridden by each descendant class, in order to specify that class's
        ClassID.

        This property has id ``1.1``.

    .. _ocadataset_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocadataset_lastmodificationtime:

    .. cpp:member:: OcaTime LastModificationTime

        Time of last modification. Optional, may be zero if not implemented.

        This property has id ``2.5``.

    .. _ocadataset_maxsize:

    .. cpp:member:: OcaUint64 MaxSize

        Maximum dataset size in bytes.

        This property has id ``2.6``.

    .. _ocadataset_name:

    .. cpp:member:: OcaString Name

        Name of dataset. Must be unique in the device.

        This property has id ``2.2``.

    .. _ocadataset_owner:

    .. cpp:member:: const OcaONo Owner

        ONo of block that contains this object

        This property has id ``2.1``.

    .. _ocadataset_readonly:

    .. cpp:member:: OcaBoolean ReadOnly

        TRUE ``=>`` dataset is read-only. Value may or may not be changed,
        depending on implementation.

        This property has id ``2.4``.

    .. _ocadataset_type:

    .. cpp:member:: OcaMimeType Type

        Type of dataset - MIME 'content-type' value. See the definition of
        **OcaMimeType**. The standard MIME types for AES70 datasets are defined
        normatively in [AES70-1(Dataset Type)].

        This property has id ``2.3``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocadataset_openread:

    .. cpp:function:: OcaStatus OpenRead(OcaLockState RequestedLockState, OcaUint64 &DatasetSize, OcaIOSessionHandle &Handle)

        Opens a reading session. Returns status = **ProcessingFailed** if handle
        pool is used up.

        This method has id ``2.1``.

        - :cpp:expr:`RequestedLockState`: Input parameter.


        - :cpp:expr:`DatasetSize`: Output parameter.


        - :cpp:expr:`Handle`: Output parameter.


    .. _ocadataset_openwrite:

    .. cpp:function:: OcaStatus OpenWrite(OcaLockState RequestedLockState, OcaUint64 &MaxPartSize, OcaIOSessionHandle &Handle)

        Opens a writing session. Returns status = **ProcessingFailed** if handle
        pool is used up.

        This method has id ``2.2``.

        - :cpp:expr:`RequestedLockState`: Input parameter.


        - :cpp:expr:`MaxPartSize`: Output parameter.


        - :cpp:expr:`Handle`: Output parameter.


    .. _ocadataset_close:

    .. cpp:function:: OcaStatus Close(OcaIOSessionHandle Handle)

        Closes a reading or writing session.

        This method has id ``2.3``.

        - :cpp:expr:`Handle`: Input parameter.


    .. _ocadataset_read:

    .. cpp:function:: OcaStatus Read(OcaIOSessionHandle Handle, OcaUint64 Position, OcaUint64 PartSize, OcaBoolean &EndOfData, OcaLongBlob &Part)

        Reads a part of the Dataset.

        This method has id ``2.4``.

        - :cpp:expr:`Handle`: Input parameter.


        - :cpp:expr:`Position`: Input parameter.


        - :cpp:expr:`PartSize`: Input parameter.


        - :cpp:expr:`EndOfData`: Output parameter.


        - :cpp:expr:`Part`: Output parameter.


    .. _ocadataset_write:

    .. cpp:function:: OcaStatus Write(OcaIOSessionHandle Handle, OcaUint64 Position, OcaLongBlob Part)

        Writes a part of the dataset.

        This method has id ``2.5``.

        - :cpp:expr:`Handle`: Input parameter.


        - :cpp:expr:`Position`: Input parameter.


        - :cpp:expr:`Part`: Input parameter.


    .. _ocadataset_clear:

    .. cpp:function:: OcaStatus Clear(OcaIOSessionHandle Handle)

        Removes all data from the dataset.

        This method has id ``2.6``.

        - :cpp:expr:`Handle`: Input parameter.


    .. _ocadataset_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        Gets the value of property **Owner**.

        This method has id ``2.7``.

        - :cpp:expr:`Owner`: Output parameter.


    .. _ocadataset_getname:

    .. cpp:function:: OcaStatus GetName(OcaString &Name)

        Gets the value of property **Name**.

        This method has id ``2.8``.

        - :cpp:expr:`Name`: Output parameter.


    .. _ocadataset_setname:

    .. cpp:function:: OcaStatus SetName(OcaString Name)

        Sets the value of property **Name**.

        This method has id ``2.9``.

        - :cpp:expr:`Name`: Input parameter.


    .. _ocadataset_gettype:

    .. cpp:function:: OcaStatus GetType(OcaString &Type)

        Gets the value of property **Type**.

        This method has id ``2.10``.

        - :cpp:expr:`Type`: Output parameter.


    .. _ocadataset_settype:

    .. cpp:function:: OcaStatus SetType(OcaString Type)

        Sets the value of property **Type** .

        This method has id ``2.11``.

        - :cpp:expr:`Type`: Input parameter.


    .. _ocadataset_getreadonly:

    .. cpp:function:: OcaStatus GetReadOnly(OcaBoolean &ReadOnly)

        Gets the value of the **Readonly** property.

        This method has id ``2.12``.

        - :cpp:expr:`ReadOnly`: Output parameter.


    .. _ocadataset_setreadonly:

    .. cpp:function:: OcaStatus SetReadOnly(OcaBoolean ReadOnly)

        Sets the value of the **Readonly** property. Optional method.

        This method has id ``2.13``.

        - :cpp:expr:`ReadOnly`: Input parameter.


    .. _ocadataset_getlastmodificationtime:

    .. cpp:function:: OcaStatus GetLastModificationTime(OcaTime &Time)

        Gets the value of property **LastModificationTime**. Optional method.

        This method has id ``2.14``.

        - :cpp:expr:`Time`: Output parameter.


    .. _ocadataset_getdatasetsizes:

    .. cpp:function:: OcaStatus GetDatasetSizes(OcaUint64 &CurrentSize, OcaUint64 &MaxSize)

        Gets current & max sizes

        This method has id ``2.15``.

        - :cpp:expr:`CurrentSize`: Output parameter.


        - :cpp:expr:`MaxSize`: Output parameter.


    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaRoot::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

