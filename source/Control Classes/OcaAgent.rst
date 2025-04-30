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

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaagent_label:

    .. cpp:member:: OcaString Label

        User-specified label.

        This property has id ``2.1``.

    .. _ocaagent_owner:

    .. cpp:member:: OcaONo Owner

        Object number of block that contains this agent.

        This property has id ``2.2``.

    Properties inherited from :ref:`ocaroot`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`


    **Methods**:


    .. _ocaagent_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the value of the Label property. The return value indicates whether
        the property was successfully retrieved.

        This method has id ``2.1``.

        - :cpp:expr:`Label`: Output parameter.


    .. _ocaagent_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the value of the Label property. The return value indicates whether
        the property was successfully set.

        This method has id ``2.2``.

        - :cpp:expr:`Label`: Input parameter.


    .. _ocaagent_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        Gets the value of the Owner property. The return value indicates whether
        the property was successfully retrieved.

        This method has id ``2.3``.

        - :cpp:expr:`owner`: Output parameter.


    .. _ocaagent_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        Returns path from the given object down to root. The return value
        indicates whether the operation succeeded. Added in version 2.

        This method has id ``2.4``.

        - :cpp:expr:`NamePath`: Output parameter.


        - :cpp:expr:`ONoPath`: Output parameter.


    Methods inherited from :ref:`ocaroot`:

    - :ref:`OcaRoot::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaRoot::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaRoot::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaRoot::Unlock <ocaroot_unlock>`

    - :ref:`OcaRoot::GetRole <ocaroot_getrole>`

    - :ref:`OcaRoot::LockReadonly <ocaroot_lockreadonly>`

