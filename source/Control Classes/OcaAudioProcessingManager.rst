.. _ocaaudioprocessingmanager:

1.3.9  OcaAudioProcessingManager
================================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaAudioProcessingManager <ocaaudioprocessingmanager>`

.. cpp:class:: OcaAudioProcessingManager: OcaManager

    Placeholder for optional manager that in future versions of the standard
    will hold various global audio processing parameters.

     - May be instantiated at most once in any device.

     - If instantiated, object number must be 9.



    **Properties**:


    .. _ocaaudioprocessingmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.9"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaaudioprocessingmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

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


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaManager::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

