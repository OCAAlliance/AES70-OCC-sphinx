.. _ocaphysicalposition:

1.2.17  OcaPhysicalPosition
===========================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaPhysicalPosition: OcaAgent

    Physical position of device or an element of it. AES70 supports a
    variety of positional coordinate systems. For details, see AES70-1,
    section 5.5.9.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaPositionCoordinateSystem CoordinateSystem

        This property has id ``3.1``.

        Type of physical coordinate system this object uses. Read-only, set at
        object construction time.

    .. cpp:member:: OcaPositionDescriptorFieldFlags PositionDescriptorFieldFlags

        This property has id ``3.2``.

        Position descriptor field flags. Describe which position descriptor
        fields are used by this object. Read-only, set at object construction
        time.

    .. cpp:member:: OcaPositionDescriptor PositionDescriptor

        This property has id ``3.3``.

        Position coordinates. For details, see AES70-1, section 5.5.9 and the
        **OcaPositionDescriptor** datatype definition.

    .. cpp:function:: OcaStatus GetCoordinateSystem(OcaPositionCoordinateSystem &CoordinateSystem)

        This method has id ``3.1``.

        Retrieves value of property **CoordinateSystem** . Result indicates
        whether retrieval was successful.

        :param OcaPositionCoordinateSystem CoordinateSystem: Output parameter.

    .. cpp:function:: OcaStatus GetPositionDescriptorFieldFlags(OcaPositionDescriptorFieldFlags &Flags)

        This method has id ``3.2``.

        Retrieves value of property **PositionDescriptorFieldFlags** . Result
        indicates whether retrieval was successful.

        :param OcaPositionDescriptorFieldFlags Flags: Output parameter.

    .. cpp:function:: OcaStatus GetPositionDescriptor(OcaPositionDescriptor &PositionDescriptor, OcaPositionDescriptor &minPositionDescriptor, OcaPositionDescriptor &maxPositionDescriptor)

        This method has id ``3.3``.

        Retrieves value of property **PositioinDescriptor** . Result indicates
        whether retrieval was successful.

        :param OcaPositionDescriptor PositionDescriptor: Output parameter.
        :param OcaPositionDescriptor minPositionDescriptor: Output parameter.
        :param OcaPositionDescriptor maxPositionDescriptor: Output parameter.

    .. cpp:function:: OcaStatus SetPositionDescriptor(OcaPositionDescriptor PositionDescriptor)

        This method has id ``3.4``.

        Sets value of property **PositionDescriptor** . Result indicates
        whether setting was successful. The **ParameterError** status is
        returned if: (a) the **FieldFlags** field of the given
        **PositionDescriptor** value differs from the object's basic position
        descriptor as given in its **PositionDescriptorFieldFlags** property,
        or (b) the given **CoordinateSystem** value conflicts with the
        object's basic coordinate system as given in its **CoordinateSystem**
        property. This is an optional method, not implemented for read-only
        position objects.

        :param OcaPositionDescriptor PositionDescriptor: Input parameter.

