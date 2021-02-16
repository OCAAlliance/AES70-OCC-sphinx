.. _ocaworker:

1.1  OcaWorker
==============

Extends :ref:`OcaRoot <ocaroot>`.

.. cpp:class:: OcaWorker: OcaRoot

    Abstract base class for classes that represent the device's
    application and support functions.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``2.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``2.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaBoolean Enabled

        This property has id ``2.0``.

        Read/write property that indicates whether the worker object is
        enabled in the device. If an object is disabled it cannot be used by
        the application. Note that the behavior of a disabled object depends
        on the object itself (e.g. a disabled chime generator is silent, a
        disabled equalizer is flat, etc.).

    .. cpp:member:: OcaList<OcaPort> Ports

        This property has id ``2.0``.

        The list of (input and output) OCA ports the worker object has. Note
        that a worker object can have no ports (in which case the list is
        empty).

    .. cpp:member:: OcaString Label

        This property has id ``2.0``.

        Specific label of the worker. Can be used to provide human readable
        information about the worker. The label can be get and set over the
        network.

    .. cpp:member:: OcaONo Owner

        This property has id ``2.0``.

        Object number of block that contains this worker.

    .. cpp:member:: OcaTimeInterval Latency

        This property has id ``2.0``.

        Processing latency of this object. Optional. Readonly or readwrite,
        depending on implementation.

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        This method has id ``2.1``.

        Gets the value of the Enabled property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaBoolean enabled: Output parameter.

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        This method has id ``2.2``.

        Sets the value of the Enabled property. The return value indicates
        whether the property was successfully set.

        :param OcaBoolean enabled: Input parameter.

    .. cpp:function:: OcaStatus AddPort(OcaString Label, OcaPortMode Mode, OcaPortID &ID)

        This method has id ``2.3``.

        Adds an input or output port.. The return value indicates whether the
        port was successfully added.

        :param OcaString Label: Input parameter.
        :param OcaPortMode Mode: Input parameter.
        :param OcaPortID ID: Output parameter.

    .. cpp:function:: OcaStatus DeletePort(OcaPortID ID)

        This method has id ``2.4``.

        Deletes an input or output port.. The return value indicates whether
        the port was successfully deleted.

        :param OcaPortID ID: Input parameter.

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        This method has id ``2.5``.

        Gets the list of ports owned by the Worker object. The return value
        indicates whether the list was successfully retrieved.

        :param OcaList<OcaPort> OcaPorts: Output parameter.

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        This method has id ``2.6``.

        Gets the name of the designated port. The return value indicates
        whether the name was successfully retrieved.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Output parameter.

    .. cpp:function:: OcaStatus SetPortName(OcaPortID PortID, OcaString Name)

        This method has id ``2.7``.

        Sets the name of the designated port. The return value indicates
        whether the name was successfully set.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Input parameter.

    .. cpp:function:: OcaStatus GetLabel(OcaString &label)

        This method has id ``2.8``.

        Gets the value of the Label property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaString label: Output parameter.

    .. cpp:function:: OcaStatus SetLabel(OcaString label)

        This method has id ``2.9``.

        Sets the value of the Label property. The return value indicates
        whether the property was successfully set.

        :param OcaString label: Input parameter.

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        This method has id ``2.10``.

        Gets the value of the Owner property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaONo owner: Output parameter.

    .. cpp:function:: OcaStatus GetLatency(OcaTimeInterval &latency)

        This method has id ``2.11``.

        Gets the value of the Latency property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaTimeInterval latency: Output parameter.

    .. cpp:function:: OcaStatus SetLatency(OcaTimeInterval latency)

        This method has id ``2.12``.

        Sets the value of the Latency property. The return value indicates
        whether the property was successfully set.

        :param OcaTimeInterval latency: Input parameter.

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        This method has id ``2.13``.

        Returns path from the given object down to root. The return value
        indicates whether the operation succeeded. Added in version 2.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.

