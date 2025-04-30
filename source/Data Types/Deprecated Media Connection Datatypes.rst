*************************************
Deprecated Media Connection Datatypes
*************************************

.. _OcaMediaConnection:

OcaMediaConnection
==================

.. cpp:struct:: OcaMediaConnection

    A single-channel or multichannel connection between a local media connector
    (i.e. **OcaMedia(Source/Sink)Connector** instance) of an
    **OcaMediaTransportNetwork** object in this node and another ("remote")
    media source or sink. Normally, the remote source or sink is in another
    node. The remote end may or may not be an OCA-compliant device. A connection
    is unidirectional. Its direction is determined by the connector that owns
    the connection. Its direction is either:

     - *Outbound: * A signal flow from a **source** connector to an external
       destination; or

     - *Inbound: * A signal flow from an external source to a **sink**
       connector.


    An **OcaMediaConnection** object may represent a connection to either a
    unicast or a multicast stream. Any given **OcaMedia(Source/Sink)Connector**
    object will only have one media connection. In non-OCA documents,
    connections are sometimes referred to as *streams* or *flows.*

    .. cpp:member:: OcaBoolean Secure

        True if and only if connection is secure.

    .. cpp:member:: OcaMediaStreamParameters StreamParameters

        Stream parameters (encoding, sampling, etc). Format is media network
        type dependent.

    .. cpp:member:: OcaMediaStreamCastMode StreamCastMode

        Unicast or multicast

    .. cpp:member:: OcaUint16 StreamChannelCount

        Number of channels in connected stream

