.. _ocadiagnosticmanager:

1.3.13  OcaDiagnosticManager
============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaManager <ocamanager>` :raw:html:`&rarr;` :ref:`OcaDiagnosticManager <ocadiagnosticmanager>` 

.. cpp:class:: OcaDiagnosticManager: OcaManager

    Optional manager that provides application diagnostic aids. Unlike other manager classes, OcaDiagnosticManager may be subclassed to provide proprietary application diagnostic enhancements.  
    
     - May be instantiated once in any device.
     
    
     - If instantiated, object number must be 13.
     

    **Properties**:

    .. _ocadiagnosticmanager_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.3.13"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocadiagnosticmanager_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``3.2``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocadiagnosticmanager_getlockstatus:

    .. cpp:function:: OcaStatus GetLockStatus(OcaONo ONo, OcaString &StatusDescription)

        Retrieves a text description of the given object's lock status. Return value indicates success of the retrieval.

        This method has id ``3.1``.

        :param OcaONo ONo: Input parameter.
        :param OcaString StatusDescription: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


