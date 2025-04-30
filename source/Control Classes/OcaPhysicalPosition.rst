.. _ocaphysicalposition:

1.2.17  OcaPhysicalPosition
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaAgent <ocaagent>` : :ref:`OcaPhysicalPosition <ocaphysicalposition>`

.. cpp:class:: OcaPhysicalPosition: OcaAgent

    Physical position of device or an element of it. AES70 supports a variety of
    positional coordinate systems. For details, see AES70-1, section 5.5.9.

    **Properties**:


    .. _ocaphysicalposition_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.2.17"

        This property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocaphysicalposition_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 1


        This property has id ``1.2``.

    .. _ocaphysicalposition_coordinatesystem:

    .. cpp:member:: const OcaPositionCoordinateSystem CoordinateSystem

        Type of physical coordinate system this object uses. Read-only, set at
        object construction time.

        This property has id ``3.1``.

    .. _ocaphysicalposition_positiondescriptorfieldflags:

    .. cpp:member:: const OcaPositionDescriptorFieldFlags PositionDescriptorFieldFlags

        Position descriptor field flags. Describe which position descriptor
        fields are used by this object. Read-only, set at object construction
        time.

        This property has id ``3.2``.

    .. _ocaphysicalposition_positiondescriptor:

    .. cpp:member:: OcaPositionDescriptor PositionDescriptor

        Position coordinates. For details, see AES70-1, section 5.5.9 and the
        **OcaPositionDescriptor** datatype definition.

        This property has id ``3.3``.

    Properties inherited from :ref:`ocaagent`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaAgent::ClassID <ocaagent_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaAgent::ClassVersion <ocaagent_classversion>`

    - :cpp:texpr:`OcaString` :ref:`OcaAgent::Label <ocaagent_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaAgent::Owner <ocaagent_owner>`


    **Methods**:


    .. _ocaphysicalposition_getcoordinatesystem:

    .. cpp:function:: OcaStatus GetCoordinateSystem(OcaPositionCoordinateSystem &CoordinateSystem)

        Retrieves value of property **CoordinateSystem**. Result indicates
        whether retrieval was successful.

        This method has id ``3.1``.

        - :cpp:expr:`CoordinateSystem`: Output parameter.


    .. _ocaphysicalposition_getpositiondescriptorfieldflags:

    .. cpp:function:: OcaStatus GetPositionDescriptorFieldFlags(OcaPositionDescriptorFieldFlags &Flags)

        Retrieves value of property **PositionDescriptorFieldFlags**. Result
        indicates whether retrieval was successful.

        This method has id ``3.2``.

        - :cpp:expr:`Flags`: Output parameter.


    .. _ocaphysicalposition_getpositiondescriptor:

    .. cpp:function:: OcaStatus GetPositionDescriptor(OcaPositionDescriptor &PositionDescriptor, OcaPositionDescriptor &minPositionDescriptor, OcaPositionDescriptor &maxPositionDescriptor)

        Retrieves value of property **PositioinDescriptor**. Result indicates
        whether retrieval was successful.

        This method has id ``3.3``.

        - :cpp:expr:`PositionDescriptor`: Output parameter.


        - :cpp:expr:`minPositionDescriptor`: Output parameter.


        - :cpp:expr:`maxPositionDescriptor`: Output parameter.


    .. _ocaphysicalposition_setpositiondescriptor:

    .. cpp:function:: OcaStatus SetPositionDescriptor(OcaPositionDescriptor PositionDescriptor)

        Sets value of property **PositionDescriptor**. Result indicates whether
        setting was successful. The **ParameterError** status is returned if:
        (a) the **FieldFlags** field of the given **PositionDescriptor** value
        differs from the object's basic position descriptor as given in its
        **PositionDescriptorFieldFlags** property, or (b) the given
        **CoordinateSystem** value conflicts with the object's basic coordinate
        system as given in its **CoordinateSystem** property. This is an
        optional method, not implemented for read-only position objects.

        This method has id ``3.4``.

        - :cpp:expr:`PositionDescriptor`: Input parameter.


    Methods inherited from :ref:`ocaagent`:

    - :ref:`OcaAgent::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaAgent::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaAgent::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaAgent::Unlock <ocaroot_unlock>`

    - :ref:`OcaAgent::GetRole <ocaroot_getrole>`

    - :ref:`OcaAgent::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaAgent::GetLabel <ocaagent_getlabel>`

    - :ref:`OcaAgent::SetLabel <ocaagent_setlabel>`

    - :ref:`OcaAgent::GetOwner <ocaagent_getowner>`

    - :ref:`OcaAgent::GetPath <ocaagent_getpath>`

