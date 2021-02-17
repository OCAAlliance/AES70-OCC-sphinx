.. _ocaphysicalposition:

1.2.17  OcaPhysicalPosition
===========================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaAgent <ocaagent>` :raw:html:`&rarr;` :ref:`OcaPhysicalPosition <ocaphysicalposition>` 

.. cpp:class:: OcaPhysicalPosition: OcaAgent

    Physical position of device or an element of it. AES70 supports a
    variety of positional coordinate systems. For details, see AES70-1,
    section 5.5.9.

    **Properties**:

    .. _ocaphysicalposition_classid:

    .. cpp:member:: OcaClassID ClassID

        This property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocaphysicalposition_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocaphysicalposition_coordinatesystem:

    .. cpp:member:: OcaPositionCoordinateSystem CoordinateSystem

        Type of physical coordinate system this object uses. Read-only, set at
        object construction time.

        This property has id ``3.1``.

    .. _ocaphysicalposition_positiondescriptorfieldflags:

    .. cpp:member:: OcaPositionDescriptorFieldFlags PositionDescriptorFieldFlags

        Position descriptor field flags. Describe which position descriptor
        fields are used by this object. Read-only, set at object construction
        time.

        This property has id ``3.2``.

    .. _ocaphysicalposition_positiondescriptor:

    .. cpp:member:: OcaPositionDescriptor PositionDescriptor

        Position coordinates. For details, see AES70-1, section 5.5.9 and the
        **OcaPositionDescriptor** datatype definition.

        This property has id ``3.3``.

    Properties inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <OcaAgent_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <OcaAgent_Owner>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocaphysicalposition_getcoordinatesystem:

    .. cpp:function:: OcaStatus GetCoordinateSystem(OcaPositionCoordinateSystem &CoordinateSystem)

        Retrieves value of property **CoordinateSystem** . Result indicates
        whether retrieval was successful.

        This method has id ``3.1``.

        :param OcaPositionCoordinateSystem CoordinateSystem: Output parameter.

    .. _ocaphysicalposition_getpositiondescriptorfieldflags:

    .. cpp:function:: OcaStatus GetPositionDescriptorFieldFlags(OcaPositionDescriptorFieldFlags &Flags)

        Retrieves value of property **PositionDescriptorFieldFlags** . Result
        indicates whether retrieval was successful.

        This method has id ``3.2``.

        :param OcaPositionDescriptorFieldFlags Flags: Output parameter.

    .. _ocaphysicalposition_getpositiondescriptor:

    .. cpp:function:: OcaStatus GetPositionDescriptor(OcaPositionDescriptor &PositionDescriptor, OcaPositionDescriptor &minPositionDescriptor, OcaPositionDescriptor &maxPositionDescriptor)

        Retrieves value of property **PositioinDescriptor** . Result indicates
        whether retrieval was successful.

        This method has id ``3.3``.

        :param OcaPositionDescriptor PositionDescriptor: Output parameter.
        :param OcaPositionDescriptor minPositionDescriptor: Output parameter.
        :param OcaPositionDescriptor maxPositionDescriptor: Output parameter.

    .. _ocaphysicalposition_setpositiondescriptor:

    .. cpp:function:: OcaStatus SetPositionDescriptor(OcaPositionDescriptor PositionDescriptor)

        Sets value of property **PositionDescriptor** . Result indicates
        whether setting was successful. The **ParameterError** status is
        returned if: (a) the **FieldFlags** field of the given
        **PositionDescriptor** value differs from the object's basic position
        descriptor as given in its **PositionDescriptorFieldFlags** property,
        or (b) the given **CoordinateSystem** value conflicts with the
        object's basic coordinate system as given in its **CoordinateSystem**
        property. This is an optional method, not implemented for read-only
        position objects.

        This method has id ``3.4``.

        :param OcaPositionDescriptor PositionDescriptor: Input parameter.


    Methods inherited from :ref:`OcaAgent <OcaAgent>`:
    
    - :ref:`OcaAgent::GetLabel(Label) <OcaAgent_GetLabel>`
    
    - :ref:`OcaAgent::SetLabel(Label) <OcaAgent_SetLabel>`
    
    - :ref:`OcaAgent::GetOwner(owner) <OcaAgent_GetOwner>`
    
    - :ref:`OcaAgent::GetPath(NamePath, ONoPath) <OcaAgent_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


