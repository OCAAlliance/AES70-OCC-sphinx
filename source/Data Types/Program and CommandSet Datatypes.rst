********************************
Program and CommandSet Datatypes
********************************

.. _OcaCommand:

OcaCommand
==========

.. cpp:struct:: OcaCommand

    A member of a CommandSet. See the datatype **OcaCommandSet**.

    .. cpp:member:: OcaMethod Method

        Method identification (ONo & ID) of method the command invokes. **nb**
        Datatype corrected to **OcaMethod** in AES70-2024.

    .. cpp:member:: OcaList<OcaLongBlob> Parameters

        Command parameters, if any. Format is method-specific. **nb** Datatype
        changed from **OcaList<OcaBlob>** to **OcaList<OcaLongBlob>** in
        AES70-2024.

