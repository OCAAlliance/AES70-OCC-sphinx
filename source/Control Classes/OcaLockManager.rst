.. _ocalockmanager:

1.3.14  OcaLockManager
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaLockManager <ocalockmanager>`

.. cpp:class:: OcaLockManager: OcaManager

    Optional object and device lock manager that supports mutex-type waits for
    locking things without causing race conditions.

     - May be instantiated at most once in any device.

     - If instantiated, object number must be 14 (decimal).



    **Properties**:


    .. _ocalockmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.14"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocalockmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocalockmanager_lockwait:

    .. cpp:function:: OcaStatus LockWait(OcaONo target, OcaLockState type, OcaTimeInterval timeout)

        Lock an object. returns when lock is set or timeout expires or
        **AbortWaits(...)** is called. A timeout value of zero requests an
        indefinite wait with no timeout.. Note: To lock an entire device, lock
        its Device Manager (ONo 1).

        This method has id ``3.1``.

        - :cpp:expr:`target`: Input parameter.


        - :cpp:expr:`type`: Input parameter.


        - :cpp:expr:`timeout`: Input parameter.


    .. _ocalockmanager_abortwaits:

    .. cpp:function:: OcaStatus AbortWaits(OcaONo ONo)

        Aborts all of this session's waits on the given object.

        This method has id ``3.2``.

        - :cpp:expr:`ONo`: Input parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

