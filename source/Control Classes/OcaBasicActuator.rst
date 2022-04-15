.. _ocabasicactuator:

1.1.1.1  OcaBasicActuator
=========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaBasicActuator <ocabasicactuator>` 

.. cpp:class:: OcaBasicActuator: OcaActuator

    Abstract base class for weakly typed actuators.

    **Properties**:

    .. _ocabasicactuator_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocabasicactuator_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:


    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


