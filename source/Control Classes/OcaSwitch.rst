.. _ocaswitch:

1.1.1.4  OcaSwitch
==================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaSwitch <ocaswitch>`

.. cpp:class:: OcaSwitch: OcaActuator

    (n)-position single-pole switch.

    **Properties**:


    .. _ocaswitch_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.4"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaswitch_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocaswitch_position:

    .. cpp:member:: OcaUint16 Position

        The current position of the switch. Positions shall be numbered from
        minPosition to (including) maxPosition. If the object does not return
        the optional parameters minPosition and maxPosition in its GetPosition
        method the positions shall be numbered from 1 to n.

        This property has id ``4.1``.

    .. _ocaswitch_positionnames:

    .. cpp:member:: OcaList<OcaString> PositionNames

        Vector of switch position names. Supplied by controller.

        This property has id ``4.2``.

    .. _ocaswitch_positionenableds:

    .. cpp:member:: OcaList<OcaBoolean> PositionEnableds

        Vector of booleans which enable or disable corresponding switch
        positions. Default values are a construction parameter. The usual
        default value is True.

        This property has id ``4.3``.

    Properties inherited from :ref:`ocaactuator`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocaswitch_getposition:

    .. cpp:function:: OcaStatus GetPosition(OcaUint16 &position, OcaUint16 &minPosition, OcaUint16 &maxPosition)

        Gets the value of the Position property and, optionally, its
        implementation min and max. The return value indicates whether the data
        was successfully retrieved.

        This method has id ``4.1``.

        - :cpp:expr:`position`: Output parameter.


        - :cpp:expr:`minPosition`: Output parameter.


        - :cpp:expr:`maxPosition`: Output parameter.


    .. _ocaswitch_setposition:

    .. cpp:function:: OcaStatus SetPosition(OcaUint16 position)

        Sets the value of the Position property. The return value indicates
        whether the property was successfully set.

        This method has id ``4.2``.

        - :cpp:expr:`position`: Input parameter.


    .. _ocaswitch_getpositionname:

    .. cpp:function:: OcaStatus GetPositionName(OcaUint16 Index, OcaString &Name)

        Gets the name assigned to a given switch position. The return value
        indicates whether the name was successfully retrieved.

        This method has id ``4.3``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Name`: Output parameter.


    .. _ocaswitch_setpositionname:

    .. cpp:function:: OcaStatus SetPositionName(OcaUint16 Index, OcaString Name)

        Assigns a name to a given switch position. The return value indicates
        whether the name was successfully assigned.

        This method has id ``4.4``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`Name`: Input parameter.


    .. _ocaswitch_getpositionnames:

    .. cpp:function:: OcaStatus GetPositionNames(OcaList<OcaString> &Names)

        Gets list of names assigned to the switch's positions. The return value
        indicates whether the names were successfully retrieved.

        This method has id ``4.5``.

        - :cpp:expr:`Names`: Output parameter.


    .. _ocaswitch_setpositionnames:

    .. cpp:function:: OcaStatus SetPositionNames(OcaList<OcaString> Names)

        Assigns names to the switch's positions. The return value indicates
        whether the names were successfully assigned.

        This method has id ``4.6``.

        - :cpp:expr:`Names`: Input parameter.


    .. _ocaswitch_getpositionenabled:

    .. cpp:function:: OcaStatus GetPositionEnabled(OcaUint16 Index, OcaBoolean &enabled)

        Gets the Enabled flag assigned to a given switch position. The return
        value indicates whether the flag was successfully retrieved.

        This method has id ``4.7``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`enabled`: Output parameter.


    .. _ocaswitch_setpositionenabled:

    .. cpp:function:: OcaStatus SetPositionEnabled(OcaUint16 Index, OcaBoolean enabled)

        Sets the Enabled flag assigned to a given switch position. The return
        value indicates whether the flag was successfully set.

        This method has id ``4.8``.

        - :cpp:expr:`Index`: Input parameter.


        - :cpp:expr:`enabled`: Input parameter.


    .. _ocaswitch_getpositionenableds:

    .. cpp:function:: OcaStatus GetPositionEnableds(OcaList<OcaBoolean> &enableds)

        Gets list of Enabled flags assigned to the switch's positions. The
        return value indicates whether the flags were successfully retrieved.

        This method has id ``4.9``.

        - :cpp:expr:`enableds`: Output parameter.


    .. _ocaswitch_setpositionenableds:

    .. cpp:function:: OcaStatus SetPositionEnableds(OcaList<OcaBoolean> enableds)

        Sets list of Enabled flags for the switch's positions. The return value
        indicates whether the flags were successfully set.

        This method has id ``4.10``.

        - :cpp:expr:`enableds`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

