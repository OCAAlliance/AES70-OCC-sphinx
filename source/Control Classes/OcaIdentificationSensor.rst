.. _ocaidentificationsensor:

1.1.2.6  OcaIdentificationSensor
================================

Extends :ref:`OcaSensor <ocasensor>`.

.. cpp:class:: OcaIdentificationSensor: OcaSensor

    Sensor for device identification mechanism. The idea of this mechanism
    is that there is some kind of control -- a pushbutton, for instance --
    that the user depresses to send a device identification event to the
    controller. Such mechanisms aid in the setup of networks.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``4.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``4.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

