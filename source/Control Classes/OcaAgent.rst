.. _ocaagent:

1.2  OcaAgent
=============

Extends :ref:`OcaRoot <ocaroot>`.

.. cpp:class:: OcaAgent: OcaRoot

    Abstract base class for defining agents.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``2.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``2.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaString Label

        This property has id ``2.1``.

        User-specified label.

    .. cpp:member:: OcaONo Owner

        This property has id ``2.2``.

        Object number of block that contains this agent.

    .. cpp:function:: OcaStatus GetLabel(OcaString &Label)

        This method has id ``2.1``.

        Gets the value of the Label property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaString Label: Output parameter.

    .. cpp:function:: OcaStatus SetLabel(OcaString Label)

        This method has id ``2.2``.

        Sets the value of the Label property. The return value indicates
        whether the property was successfully set.

        :param OcaString Label: Input parameter.

    .. cpp:function:: OcaStatus GetOwner(OcaONo &owner)

        This method has id ``2.3``.

        Gets the value of the Owner property. The return value indicates
        whether the property was successfully retrieved.

        :param OcaONo owner: Output parameter.

    .. cpp:function:: OcaStatus GetPath(OcaNamePath &NamePath, OcaONoPath &ONoPath)

        This method has id ``2.4``.

        Returns path from the given object down to root. The return value
        indicates whether the operation succeeded. Added in version 2.

        :param OcaNamePath NamePath: Output parameter.
        :param OcaONoPath ONoPath: Output parameter.

