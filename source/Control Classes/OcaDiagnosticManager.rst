.. _ocadiagnosticmanager:

1.3.13  OcaDiagnosticManager
============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaManager <ocamanager>` : :ref:`OcaDiagnosticManager <ocadiagnosticmanager>`

.. cpp:class:: OcaDiagnosticManager: OcaManager

    Optional manager that provides application diagnostic aids. Unlike other
    manager classes, OcaDiagnosticManager may be subclassed to provide
    proprietary application diagnostic enhancements.

     - May be instantiated once in any device.

     - If instantiated, object number must be 13.



    **Properties**:


    .. _ocadiagnosticmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.13"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadiagnosticmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    Properties inherited from :ref:`ocamanager`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaManager::ClassID <ocamanager_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaManager::ClassVersion <ocamanager_classversion>`


    **Methods**:


    .. _ocadiagnosticmanager_getlockstatus:

    .. cpp:function:: OcaStatus GetLockStatus(OcaONo ONo, OcaString &StatusDescription)

        Retrieves a text description of the given object's lock status. Return
        value indicates success of the retrieval.

        This method has id ``3.1``.

        - :cpp:expr:`ONo`: Input parameter.


        - :cpp:expr:`StatusDescription`: Output parameter.


    Methods inherited from :ref:`ocamanager`:

    - :ref:`OcaManager::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaManager::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaManager::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaManager::Unlock <ocaroot_unlock>`

    - :ref:`OcaManager::GetRole <ocaroot_getrole>`

    - :ref:`OcaManager::LockReadonly <ocaroot_lockreadonly>`

