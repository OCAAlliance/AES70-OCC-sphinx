**************
When datatypes
**************

.. _OcaWhenPhysicalAbsolute:

OcaWhenPhysicalAbsolute
=======================

.. cpp:struct:: OcaWhenPhysicalAbsolute

    Absolute physical time.

    .. cpp:member:: OcaONo TimeRefONo

        ONo of an **OcaTimeSource** object or zero to use device time - 4 bytes

    .. cpp:member:: OcaTime Value

        Absolute physical time.

.. _OcaWhenPhysicalRelative:

OcaWhenPhysicalRelative
=======================

.. cpp:struct:: OcaWhenPhysicalRelative

    Physical time relative to time of method call.

    .. cpp:member:: OcaONo TimeRefONo

        ONo of an **OcaTimeSource** object or zero to use device time

    .. cpp:member:: OcaTime Value

        Time relative to time when method using this datatype was called

.. _OcaWhen:

OcaWhen
=======

.. cpp:type:: OcaWhen = OcaVariant<OcaWhenPhysicalAbsolute, OcaWhenPhysicalRelative>

    When something happens

