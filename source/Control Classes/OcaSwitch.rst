.. _ocaswitch:

1.1.1.4  OcaSwitch
==================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaSwitch: OcaActuator

    (n)-position single-pole switch.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaUint16 Position

        This property has id ``4.0``.

        The current position of the switch. Positions shall be numbered from
        minPosition to (including) maxPosition. If the object does not return
        the optional parameters minPosition and maxPosition in its GetPosition
        method the positions shall be numbered from 1 to n.

    .. cpp:member:: OcaList<OcaString> PositionNames

        This property has id ``4.0``.

        Vector of switch position names. Supplied by controller.

    .. cpp:member:: OcaList<OcaBoolean> PositionEnableds

        This property has id ``4.0``.

        Vector of booleans which enable or disable corresponding switch
        positions. Default values are a construction parameter. The usual
        default value is True.

    .. cpp:function:: OcaStatus GetPosition(OcaUint16 &position, OcaUint16 &minPosition, OcaUint16 &maxPosition)

        This method has id ``4.1``.

        Gets the value of the Position property and, optionally, its
        implementation min and max. The return value indicates whether the
        data was successfully retrieved.

        :param OcaUint16 position: Output parameter.
        :param OcaUint16 minPosition: Output parameter.
        :param OcaUint16 maxPosition: Output parameter.

    .. cpp:function:: OcaStatus SetPosition(OcaUint16 position)

        This method has id ``4.2``.

        Sets the value of the Position property. The return value indicates
        whether the property was successfully set.

        :param OcaUint16 position: Input parameter.

    .. cpp:function:: OcaStatus GetPositionName(OcaUint16 Index, OcaString &Name)

        This method has id ``4.3``.

        Gets the name assigned to a given switch position. The return value
        indicates whether the name was successfully retrieved.

        :param OcaUint16 Index: Input parameter.
        :param OcaString Name: Output parameter.

    .. cpp:function:: OcaStatus SetPositionName(OcaUint16 Index, OcaString Name)

        This method has id ``4.4``.

        Assigns a name to a given switch position. The return value indicates
        whether the name was successfully assigned.

        :param OcaUint16 Index: Input parameter.
        :param OcaString Name: Input parameter.

    .. cpp:function:: OcaStatus GetPositionNames(OcaList<OcaString> &Names)

        This method has id ``4.5``.

        Gets list of names assigned to the switch's positions. The return
        value indicates whether the names were successfully retrieved.

        :param OcaList<OcaString> Names: Output parameter.

    .. cpp:function:: OcaStatus SetPositionNames(OcaList<OcaString> Names)

        This method has id ``4.6``.

        Assigns names to the switch's positions. The return value indicates
        whether the names were successfully assigned.

        :param OcaList<OcaString> Names: Input parameter.

    .. cpp:function:: OcaStatus GetPositionEnabled(OcaUint16 Index, OcaBoolean &enabled)

        This method has id ``4.7``.

        Gets the Enabled flag assigned to a given switch position. The return
        value indicates whether the flag was successfully retrieved.

        :param OcaUint16 Index: Input parameter.
        :param OcaBoolean enabled: Output parameter.

    .. cpp:function:: OcaStatus SetPositionEnabled(OcaUint16 Index, OcaBoolean enabled)

        This method has id ``4.8``.

        Sets the Enabled flag assigned to a given switch position. The return
        value indicates whether the flag was successfully set.

        :param OcaUint16 Index: Input parameter.
        :param OcaBoolean enabled: Input parameter.

    .. cpp:function:: OcaStatus GetPositionEnableds(OcaList<OcaBoolean> &enableds)

        This method has id ``4.9``.

        Gets list of Enabled flags assigned to the switch's positions. The
        return value indicates whether the flags were successfully retrieved.

        :param OcaList<OcaBoolean> enableds: Output parameter.

    .. cpp:function:: OcaStatus SetPositionEnableds(OcaList<OcaBoolean> enableds)

        This method has id ``4.10``.

        Sets list of Enabled flags for the switch's positions. The return
        value indicates whether the flags were successfully set.

        :param OcaList<OcaBoolean> enableds: Input parameter.

