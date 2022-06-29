.. _ocapanbalance:

1.1.1.6  OcaPanBalance
======================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaPanBalance <ocapanbalance>` 

.. cpp:class:: OcaPanBalance: OcaActuator

    Pan or Balance control.

    **Properties**:

    .. _ocapanbalance_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.6"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocapanbalance_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocapanbalance_position:

    .. cpp:member:: OcaFloat32 Position

        Pan position. Range = -1.0 to +1.0. -1.0 is 100% left, +1.0 is 100% right.

        This property has id ``4.1``.

    .. _ocapanbalance_midpointgain:

    .. cpp:member:: OcaDB MidpointGain

        Midpoint gain. Normally, max=0dB, min=-6dB. May be readonly for pan/balance objects with fixed midpoint gains.

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

    .. _ocapanbalance_getposition:

    .. cpp:function:: OcaStatus GetPosition(OcaFloat32 &Position, OcaFloat32 &minPosition, OcaFloat32 &maxPosition)

        Gets the value and limits of the Position property. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.1``.

        :param OcaFloat32 Position: Output parameter.
        :param OcaFloat32 minPosition: Output parameter.
        :param OcaFloat32 maxPosition: Output parameter.

    .. _ocapanbalance_setposition:

    .. cpp:function:: OcaStatus SetPosition(OcaFloat32 Position)

        Sets the value of the Position property. The return value indicates whether the property was successfully set.

        This method has id ``4.2``.

        :param OcaFloat32 Position: Input parameter.

    .. _ocapanbalance_getmidpointgain:

    .. cpp:function:: OcaStatus GetMidpointGain(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the value and limits of the MidpointGain property. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.3``.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. _ocapanbalance_setmidpointgain:

    .. cpp:function:: OcaStatus SetMidpointGain(OcaDB Gain)

        Sets the value of the MidpointGain property. The return value indicates whether the property was successfully set.

        This method has id ``4.4``.

        :param OcaDB Gain: Input parameter.


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
    
    


