.. _ocaagent:

1.2  OcaAgent
=============

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` 

.. cpp:class:: OcaAgent: OcaRoot

    Abstract base class for defining agents.

    **Properties**:

    .. _ocaagent_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``2.1``.

    .. _ocaagent_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``2.2``.

    .. _ocaagent_label:

    .. cpp:member:: OcaString Label

        User-specified label.

        This property has id ``2.1``.

    .. _ocaagent_owner:

    .. cpp:member:: OcaONo Owner

        Object number of block that contains this agent.

        This property has id ``2.2``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocaagent_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        Gets the value of the Label property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.1``.

        :param OcaString Label: Output parameter.

    .. _ocaagent_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        Sets the value of the Label property. The return value indicates whether the property was successfully set.

        This method has id ``2.2``.

        :param OcaString Label: Input parameter.

    .. _ocaagent_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        Gets the value of the Owner property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.3``.

        :param OcaONo owner: Output parameter.

    .. _ocaagent_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        Returns path from the given object down to root. The return value indicates whether the operation succeeded. Added in version 2.

        This method has id ``2.4``.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


