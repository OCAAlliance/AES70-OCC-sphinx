.. _ocaswitch:

1.1.1.4  OcaSwitch
==================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaSwitch <ocaswitch>` 

.. cpp:class:: OcaSwitch: OcaActuator

    (n)-position single-pole switch.

    **Properties**:

    .. _ocaswitch_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.4"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocaswitch_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocaswitch_position:

    .. cpp:member:: OcaUint16 Position

        The current position of the switch. Positions shall be numbered from minPosition to (including) maxPosition. If the object does not return the optional parameters minPosition and maxPosition in its GetPosition method the positions shall be numbered from 1 to n.

        This property has id ``4.1``.

    .. _ocaswitch_positionnames:

    .. cpp:member:: OcaList<OcaString> PositionNames

        Vector of switch position names. Supplied by controller.

        This property has id ``4.2``.

    .. _ocaswitch_positionenableds:

    .. cpp:member:: OcaList<OcaBoolean> PositionEnableds

        Vector of booleans which enable or disable corresponding switch positions. Default values are a construction parameter. The usual default value is True.

        This property has id ``4.3``.

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

    .. _ocaswitch_getposition:

    .. cpp:function:: OcaStatus GetPosition(OcaUint16 &position, OcaUint16 &minPosition, OcaUint16 &maxPosition)

        Gets the value of the Position property and, optionally, its implementation min and max. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.1``.

        :param OcaUint16 position: Output parameter.
        :param OcaUint16 minPosition: Output parameter.
        :param OcaUint16 maxPosition: Output parameter.

    .. _ocaswitch_setposition:

    .. cpp:function:: OcaStatus SetPosition(OcaUint16 position)

        Sets the value of the Position property. The return value indicates whether the property was successfully set.

        This method has id ``4.2``.

        :param OcaUint16 position: Input parameter.

    .. _ocaswitch_getpositionname:

    .. cpp:function:: OcaStatus GetPositionName(OcaUint16 Index, OcaString &Name)

        Gets the name assigned to a given switch position. The return value indicates whether the name was successfully retrieved.

        This method has id ``4.3``.

        :param OcaUint16 Index: Input parameter.
        :param OcaString Name: Output parameter.

    .. _ocaswitch_setpositionname:

    .. cpp:function:: OcaStatus SetPositionName(OcaUint16 Index, OcaString Name)

        Assigns a name to a given switch position. The return value indicates whether the name was successfully assigned.

        This method has id ``4.4``.

        :param OcaUint16 Index: Input parameter.
        :param OcaString Name: Input parameter.

    .. _ocaswitch_getpositionnames:

    .. cpp:function:: OcaStatus GetPositionNames(OcaList<OcaString> &Names)

        Gets list of names assigned to the switch's positions. The return value indicates whether the names were successfully retrieved.

        This method has id ``4.5``.

        :param OcaList<OcaString> Names: Output parameter.

    .. _ocaswitch_setpositionnames:

    .. cpp:function:: OcaStatus SetPositionNames(OcaList<OcaString> Names)

        Assigns names to the switch's positions. The return value indicates whether the names were successfully assigned.

        This method has id ``4.6``.

        :param OcaList<OcaString> Names: Input parameter.

    .. _ocaswitch_getpositionenabled:

    .. cpp:function:: OcaStatus GetPositionEnabled(OcaUint16 Index, OcaBoolean &enabled)

        Gets the Enabled flag assigned to a given switch position. The return value indicates whether the flag was successfully retrieved.

        This method has id ``4.7``.

        :param OcaUint16 Index: Input parameter.
        :param OcaBoolean enabled: Output parameter.

    .. _ocaswitch_setpositionenabled:

    .. cpp:function:: OcaStatus SetPositionEnabled(OcaUint16 Index, OcaBoolean enabled)

        Sets the Enabled flag assigned to a given switch position. The return value indicates whether the flag was successfully set.

        This method has id ``4.8``.

        :param OcaUint16 Index: Input parameter.
        :param OcaBoolean enabled: Input parameter.

    .. _ocaswitch_getpositionenableds:

    .. cpp:function:: OcaStatus GetPositionEnableds(OcaList<OcaBoolean> &enableds)

        Gets list of Enabled flags assigned to the switch's positions. The return value indicates whether the flags were successfully retrieved.

        This method has id ``4.9``.

        :param OcaList<OcaBoolean> enableds: Output parameter.

    .. _ocaswitch_setpositionenableds:

    .. cpp:function:: OcaStatus SetPositionEnableds(OcaList<OcaBoolean> enableds)

        Sets list of Enabled flags for the switch's positions. The return value indicates whether the flags were successfully set.

        This method has id ``4.10``.

        :param OcaList<OcaBoolean> enableds: Input parameter.


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
    
    


