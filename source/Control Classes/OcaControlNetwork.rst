.. _ocacontrolnetwork:

1.4.1  OcaControlNetwork
========================

Extends :ref:`OcaApplicationNetwork <ocaapplicationnetwork>`.

.. cpp:class:: OcaControlNetwork: OcaApplicationNetwork


    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        This property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaNetworkControlProtocol Protocol

        This property has id ``3.0``.

        Type of control protocol used by the network (OCAnn). Read-only
        property.

    .. cpp:function:: OcaStatus GetControlProtocol(OcaNetworkControlProtocol &Protocol)

        This method has id ``3.1``.

        Gets the network's Protocol property. Return status indicates whether
        the operation was successful.

        :param OcaNetworkControlProtocol Protocol: Output parameter.

