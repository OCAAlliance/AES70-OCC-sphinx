.. _ocaworker:

1.1  OcaWorker
==============

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` 

.. cpp:class:: OcaWorker: OcaRoot

    Abstract base class for classes that represent the device's application and support functions.

    **Properties**:

    .. _ocaworker_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This is a class property instead of an object property. This property is an override of the  **OcaRoot** property.

        This property has id ``2.1``.

    .. _ocaworker_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``2.2``.

    .. _ocaworker_enabled:

    .. cpp:member:: OcaBoolean Enabled

        Read/write property that indicates whether the worker object is enabled in the device. If an object is disabled it cannot be used by the application. Note that the behavior of a disabled object depends on the object itself (e.g. a disabled chime generator is silent, a disabled equalizer is flat, etc.).

        This property has id ``2.1``.

    .. _ocaworker_ports:

    .. cpp:member:: OcaList<OcaPort> Ports

        The list of (input and output) OCA ports the worker object has. Note that a worker object can have no ports (in which case the list is empty).

        This property has id ``2.2``.

    .. _ocaworker_label:

    .. cpp:member:: OcaString Label

        Specific label of the worker. Can be used to provide human readable information about the worker. The label can be get and set over the network.

        This property has id ``2.3``.

    .. _ocaworker_owner:

    .. cpp:member:: OcaONo Owner

        Object number of block that contains this worker.

        This property has id ``2.4``.

    .. _ocaworker_latency:

    .. cpp:member:: OcaTimeInterval Latency

        Processing latency of this object. Optional. Readonly or readwrite, depending on implementation.

        This property has id ``2.5``.

    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocaworker_getenabled:

    .. cpp:function:: OcaStatus GetEnabled(OcaBoolean &enabled)

        Gets the value of the Enabled property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.1``.

        :param OcaBoolean enabled: Output parameter.

    .. _ocaworker_setenabled:

    .. cpp:function:: OcaStatus SetEnabled(OcaBoolean enabled)

        Sets the value of the Enabled property. The return value indicates whether the property was successfully set.

        This method has id ``2.2``.

        :param OcaBoolean enabled: Input parameter.

    .. _ocaworker_addport:

    .. cpp:function:: OcaStatus AddPort(OcaString Label, OcaPortMode Mode, OcaPortID &ID)

        Adds an input or output port.. The return value indicates whether the port was successfully added.

        This method has id ``2.3``.

        :param OcaString Label: Input parameter.
        :param OcaPortMode Mode: Input parameter.
        :param OcaPortID ID: Output parameter.

    .. _ocaworker_deleteport:

    .. cpp:function:: OcaStatus DeletePort(OcaPortID ID)

        Deletes an input or output port.. The return value indicates whether the port was successfully deleted.

        This method has id ``2.4``.

        :param OcaPortID ID: Input parameter.

    .. _ocaworker_getports:

    .. cpp:function:: OcaStatus GetPorts(OcaList<OcaPort> &OcaPorts)

        Gets the list of ports owned by the Worker object. The return value indicates whether the list was successfully retrieved.

        This method has id ``2.5``.

        :param OcaList<OcaPort> OcaPorts: Output parameter.

    .. _ocaworker_getportname:

    .. cpp:function:: OcaStatus GetPortName(OcaPortID PortID, OcaString &Name)

        Gets the name of the designated port. The return value indicates whether the name was successfully retrieved.

        This method has id ``2.6``.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Output parameter.

    .. _ocaworker_setportname:

    .. cpp:function:: OcaStatus SetPortName(OcaPortID PortID, OcaString Name)

        Sets the name of the designated port. The return value indicates whether the name was successfully set.

        This method has id ``2.7``.

        :param OcaPortID PortID: Input parameter.
        :param OcaString Name: Input parameter.

    .. _ocaworker_getlabel:

    .. cpp:function:: OcaStatus GetLabel(OcaString &label)

        Gets the value of the Label property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.8``.

        :param OcaString label: Output parameter.

    .. _ocaworker_setlabel:

    .. cpp:function:: OcaStatus SetLabel(OcaString label)

        Sets the value of the Label property. The return value indicates whether the property was successfully set.

        This method has id ``2.9``.

        :param OcaString label: Input parameter.

    .. _ocaworker_getowner:

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        Gets the value of the Owner property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.10``.

        :param OcaONo owner: Output parameter.

    .. _ocaworker_getlatency:

    .. cpp:function:: OcaStatus GetLatency(OcaTimeInterval &latency)

        Gets the value of the Latency property. The return value indicates whether the property was successfully retrieved.

        This method has id ``2.11``.

        :param OcaTimeInterval latency: Output parameter.

    .. _ocaworker_setlatency:

    .. cpp:function:: OcaStatus SetLatency(OcaTimeInterval latency)

        Sets the value of the Latency property. The return value indicates whether the property was successfully set.

        This method has id ``2.12``.

        :param OcaTimeInterval latency: Input parameter.

    .. _ocaworker_getpath:

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        Returns path from the given object down to root. The return value indicates whether the operation succeeded. Added in version 2.

        This method has id ``2.13``.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.


    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


