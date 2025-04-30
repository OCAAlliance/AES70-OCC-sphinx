.. _ocaagent:

1.2  OcaAgent
=============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>`

.. cpp:class:: OcaAgent: OcaRoot

    Abstract base class for defining agents.

    **Properties**:


    .. _ocaagent_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaagent_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaagent_label:

    .. cpp:member:: OcaString Label

        User-specified label.

        This property has id ``2.1``.

    .. _ocaagent_owner:

    .. cpp:member:: const OcaONo Owner

        Object number of block that contains this agent. Readonly.

        This property has id ``2.2``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocaagent_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the value of the **Label** property.

        This method has id ``2.1``.

        - :cpp:expr:`Label`: Output parameter.


    .. _ocaagent_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the value of the **Label** property.

        This method has id ``2.2``.

        - :cpp:expr:`Label`: Input parameter.


    .. _ocaagent_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &Owner)

        Gets the value of the **Owner** property.

        This method has id ``2.3``.

        - :cpp:expr:`Owner`: Output parameter.


    .. _ocaagent_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaRolePath &RolePath, OcaONoPath &ONoPath)

        Returns Role Path and ONo Path from the Root Block to this object. The
        return value indicates whether the operation succeeded.

        This method has id ``2.4``.

        - :cpp:expr:`RolePath`: Output parameter.


        - :cpp:expr:`ONoPath`: Output parameter.


    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaRoot::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

