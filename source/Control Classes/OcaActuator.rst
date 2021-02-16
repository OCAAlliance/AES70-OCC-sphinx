.. _ocaactuator:

1.1.1  OcaActuator
==================

Extends :ref:`OcaWorker <ocaworker>`.

.. cpp:class:: OcaActuator: OcaWorker

    Abstract base class for all actuators (i.e. devices that affect the
    routing and/or content of the audio signal, or provide ancillary
    functions such as power).

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

