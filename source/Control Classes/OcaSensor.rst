.. _ocasensor:

1.1.2  OcaSensor
================

Extends :ref:`OcaWorker <ocaworker>`.

.. cpp:class:: OcaSensor: OcaWorker

    Abstract base class for all sensor classes.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This is a
        class property instead of an object property. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaSensorReadingState ReadingState

        This property has id ``3.0``.

        Enum that describes whether current reading value is valid and if not,
        why not. Readonly.

    .. cpp:function:: OcaStatus GetReadingState(OcaSensorReadingState &state)

        This method has id ``3.1``.

        Gets the current reading state of the sensor. The return value
        indicates whether the state was successfully retrived.

        :param OcaSensorReadingState state: Output parameter.

