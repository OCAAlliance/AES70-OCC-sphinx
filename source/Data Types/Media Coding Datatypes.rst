**********************
Media Coding Datatypes
**********************

.. _OcaMediaCoding:

OcaMediaCoding
==============

.. cpp:struct:: OcaMediaCoding
    
    Codec ID + Coding parameters

    .. cpp:member:: OcaMediaCodingSchemeID CodingSchemeID

        ID of coding scheme to use.

    .. cpp:member:: OcaString CodecParameters

        Coding parameters. Content is coding-scheme-dependent.

    .. cpp:member:: OcaONo ClockONo

        Object number of OcaMediaClock3 object to use for this coding scheme. May be zero if no OcaMediaClock3 object is used.


OCP.1 Encoding
--------------

===================== ========== ===========
Field                 Basic type Byte length
===================== ========== ===========
CodingSchemeID.Value  OcaUint16  2          
CodecParameters.Len   OcaUint16  2          
CodecParameters.Value string     variable   
ClockONo.ONo          OcaUint32  4          
===================== ========== ===========


.. _OcaMediaCodingSchemeID:

OcaMediaCodingSchemeID
======================

.. cpp:type:: OcaMediaCodingSchemeID = OcaUint16

    Codec parameters
.. _OcaSDPString:

OcaSDPString
============

.. cpp:type:: OcaSDPString = OcaString

    Codec parameters