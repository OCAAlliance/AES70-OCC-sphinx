.. _ocaeventhandler:

1.2.8  OcaEventHandler
======================

Extends :ref:`OcaAgent <ocaagent>`.

.. cpp:class:: OcaEventHandler: OcaAgent

    Base class for event handler objects. This class applies to
    controllers that subscribe to events and receive notifications for
    them. Controller developers can derive from this class and add
    specific callback methods that perform processing and/or have specific
    event data structures.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:function:: OcaStatus OnEvent(OcaBlob Context, OcaEventData eventData)

        This method has id ``3.1``.

        Generic empty callback method for events. Application developers can
        override this method in a derived class to add behavior.

        :param OcaBlob Context: Input parameter.
        :param OcaEventData eventData: Input parameter.

