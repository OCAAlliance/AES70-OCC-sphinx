.. _ocamatrix:

1.1.5  OcaMatrix
================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaMatrix <ocamatrix>`

.. cpp:class:: OcaMatrix: OcaWorker

    Rectangular array of identical objects (**Matrix Members,** or just****
    **Members** in context) that is coordinate addressable and has sets of
    common input and output ports. An **OcaMatrix** instance is a container for
    a two-dimensional collection of members. Matrix members may be workers
    (including blocks or other matrices), or agents. All members of a given
    matrix shall be of the same class (*the* **member class**). No object shall
    belong to more than one matrix at a time. No object shall appear more than
    once in a given matrix. The **OcaMatrix** object shall not instantiate the
    Members, but instead shall provide the coordinate addressing, implement the
    common input and output ports, and provide certain other aggregate
    functions. The term M**atrix** means an **OcaMatrix** object *plus* the
    ancillary objects that collectively provide matrixing functionality.
    Specifically, a Matrix shall consists of: 1. One instance of the
    **OcaMatrix** class (the **matrix object**); and 2. **(N x M) members**,
    where each member shall be an instance of the member class; and The
    normative specification of the **OcaMatrix** class is here. The normative
    specification of the overall Matrix mechanism, with informative examples, is
    in [AES70-1(Matrices)].

    **Properties**:


    .. _ocamatrix_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.5"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocamatrix_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 4

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocamatrix_members:

    .. cpp:member:: OcaList2D<OcaONo> Members

        2D array of Member object numbers. A zero value shall indicate the
        absence of a Member at the position in question.

        This property has id ``3.5``.

    .. _ocamatrix_proxy:

    .. cpp:member:: OcaONo Proxy

        Object number of the Matrix Proxy. **Deprecated** in version 4 of this
        class (AES70-2024).

        This property has id ``3.6``.

    .. _ocamatrix_x:

    .. cpp:member:: OcaMatrixCoordinate X

        Active column index. The active column is the column to which matrix
        proxy method calls will be reflected. Value is zero-relative, i.e. the
        first column is number zero. A value of 65535 means all columns in the
        matrix. **Deprecated** in version 4 of this class (AES70-2024).

        This property has id ``3.1``.

    .. _ocamatrix_xsize:

    .. cpp:member:: OcaMatrixCoordinate xSize

        Number of columns in the matrix. Readonly in some cases.

        This property has id ``3.3``.

    .. _ocamatrix_y:

    .. cpp:member:: OcaMatrixCoordinate Y

        Active row index. The active row is the row to which matrix proxy
        changes will be reflected. Value is zero-relative, i.e. the first row is
        number zero. A value of 65535 means all rows in the matrix.
        **Deprecated** in version 4 of this class (AES70-2024).

        This property has id ``3.2``.

    .. _ocamatrix_ysize:

    .. cpp:member:: OcaMatrixCoordinate ySize

        Number of rows in the matrix. Readonly in some cases.

        This property has id ``3.4``.

    Properties inherited from :ref:`ocaworker`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaLockState` :ref:`OcaRoot::LockState <ocaroot_lockstate>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaMap<OcaPortID, OcaPortClockMapEntry>` :ref:`OcaWorker::PortClockMap <ocaworker_portclockmap>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`


    **Methods**:


    .. _ocamatrix_getcurrentxy:

    .. cpp:function:: OcaStatus GetCurrentXY(OcaMatrixCoordinate &x, OcaMatrixCoordinate &y)

        Gets coordinates of the currently active area (cell, row, column, or
        whole matrix). See the definitions of the properties **X** and **Y** for
        specification of X and Y values.

        This method has id ``3.1``.

        - :cpp:expr:`x`: Output parameter.


        - :cpp:expr:`y`: Output parameter.


    .. _ocamatrix_setcurrentxy:

    .. cpp:function:: OcaStatus SetCurrentXY(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        Sets the currently active area (cell, row, column, or whole matrix).
        Automatically locks the **OcaMatrix** object and the Matrix Proxy
        object. Does not lock the addressed matrix Members. Locks shall persist
        until any matrix proxy method is called in the same Control Session. See
        the definitions of the properties **X** and **Y** for specification of X
        and Y values.

        This method has id ``3.2``.

        - :cpp:expr:`x`: Input parameter.


        - :cpp:expr:`y`: Input parameter.


    .. _ocamatrix_getsize:

    .. cpp:function:: OcaStatus GetSize(OcaMatrixCoordinate &xSize, OcaMatrixCoordinate &ySize, OcaMatrixCoordinate &minXSize, OcaMatrixCoordinate &maxXSize, OcaMatrixCoordinate &minYSize, OcaMatrixCoordinate &maxYSize)

        Gets the matrix size.

        This method has id ``3.3``.

        - :cpp:expr:`xSize`: Output parameter.


        - :cpp:expr:`ySize`: Output parameter.


        - :cpp:expr:`minXSize`: Output parameter.


        - :cpp:expr:`maxXSize`: Output parameter.


        - :cpp:expr:`minYSize`: Output parameter.


        - :cpp:expr:`maxYSize`: Output parameter.


    .. _ocamatrix_setsize:

    .. cpp:function:: OcaStatus SetSize(OcaMatrixCoordinate xSize, OcaMatrixCoordinate ySize)

        Sets the matrix size. This method will not be available for fixed-size
        matrices.

        This method has id ``3.4``.

        - :cpp:expr:`xSize`: Input parameter.


        - :cpp:expr:`ySize`: Input parameter.


    .. _ocamatrix_getmembers:

    .. cpp:function:: OcaStatus GetMembers(OcaList2D<OcaONo> &members)

        Retrieves the 2D array of Member ONos. Cells for which no Member has
        been provided will contain the value zero.

        This method has id ``3.5``.

        - :cpp:expr:`members`: Output parameter.


    .. _ocamatrix_setmembers:

    .. cpp:function:: OcaStatus SetMembers(OcaList2D<OcaONo> members)

        Sets the entire 2D array of Member Object Numbers. Row and column
        dimensions of the M**embers** parameter shall be equal to the current
        row and column counts of the Matrix. In the list, a Member Object Number
        value of zero shall remove any Member at the given position.

        This method has id ``3.6``.

        - :cpp:expr:`members`: Input parameter.


    .. _ocamatrix_getmember:

    .. cpp:function:: OcaStatus GetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo &memberONo)

        Retrieves the object number of the Member at position (x,y). If no
        Member is defined at this position, shall return the value zero.

        This method has id ``3.7``.

        - :cpp:expr:`x`: Input parameter.


        - :cpp:expr:`y`: Input parameter.


        - :cpp:expr:`memberONo`: Output parameter.


    .. _ocamatrix_setmember:

    .. cpp:function:: OcaStatus SetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo memberONo)

        Installs a particular object as a Member at position (x,y). If another
        object is already at this position, it is replaced. If value of the
        **memberONo** parameter is zero, any object already at this position is
        removed and not replaced.

        This method has id ``3.8``.

        - :cpp:expr:`x`: Input parameter.


        - :cpp:expr:`y`: Input parameter.


        - :cpp:expr:`memberONo`: Input parameter.


    .. _ocamatrix_getproxy:

    .. cpp:function:: OcaStatus GetProxy(OcaONo &ONo)

        Gets the object number of the Matrix Proxy.

        This method has id ``3.9``.

        - :cpp:expr:`ONo`: Output parameter.


    .. _ocamatrix_setproxy:

    .. cpp:function:: OcaStatus SetProxy(OcaONo ONo)

        Sets the object number of the Matrix Proxy.

        This method has id ``3.10``.

        - :cpp:expr:`ONo`: Input parameter.


    .. _ocamatrix_getportsperrow:

    .. cpp:function:: OcaStatus GetPortsPerRow(OcaUint8 &Ports)

        Gets the number of Ports per row. Note: these are Input Ports.

        This method has id ``3.11``.

        - :cpp:expr:`Ports`: Output parameter.


    .. _ocamatrix_setportsperrow:

    .. cpp:function:: OcaStatus SetPortsPerRow(OcaUint8 Ports)

        Sets the number of Ports per row. These shall be Input Ports.

        This method has id ``3.12``.

        - :cpp:expr:`Ports`: Input parameter.


    .. _ocamatrix_getportspercolumn:

    .. cpp:function:: OcaStatus GetPortsPerColumn(OcaUint8 &Ports)

        Gets the number of Ports per column. Note: these are Output Ports.

        This method has id ``3.13``.

        - :cpp:expr:`Ports`: Output parameter.


    .. _ocamatrix_setportspercolumn:

    .. cpp:function:: OcaStatus SetPortsPerColumn(OcaUint8 Ports)

        Sets the number of Ports per column. These shall be Output Ports.

        This method has id ``3.14``.

        - :cpp:expr:`Ports`: Input parameter.


    .. _ocamatrix_setcurrentxylock:

    .. cpp:function:: OcaStatus SetCurrentXYLock(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        Sets the currently active area (cell, row, column, or whole matrix),
        locks the **OcaMatrix** object, locks the Matrix Proxy object, and locks
        all the Members in the active area. Fails if the referenced members
        cannot all be locked. The **OcaMatrix** and Matrix Proxy locks shall
        persist until any Matrix Proxy method is called in the same Control
        Session. The Member locks shall persist until unlocked by calls to their
        **Unlock()** methods or by a call to the **OcaMatrix** method
        **UnlockCurrent**. The returned status indicates whether the operation
        was successful. See the definitions of the properties **X** and **Y**
        for specification of X and Y values.

        This method has id ``3.15``.

        - :cpp:expr:`x`: Input parameter.


        - :cpp:expr:`y`: Input parameter.


    .. _ocamatrix_unlockcurrent:

    .. cpp:function:: OcaStatus UnlockCurrent()

        Unlocks the Member objects in the currently active area of the Matrix.
        Succeeds only if all the Members of the currently active area can be
        unlocked. Failure shall not be**** triggered if one or more Members of
        the currently active area are already unlocked. The returned status
        indicates whether the operation was successful.

        This method has id ``3.16``.

    .. _ocamatrix_executemethod:

    .. cpp:function:: OcaStatus ExecuteMethod(OcaList32<OcaMatrixCoordinates> TargetMembers, OcaMethodID TargetMethod, OcaList<OcaLongBlob> InData, OcaList<OcaCommandResult> &Results)

        Execute the same method in various Matrix Members with a common set of
        input parameters. Return the status and returned parameter values from
        each call. When an addressed Member is a Block, this method shall not be
        capable of executing methods of objects inside the Block. The
        **OcaStatus** value returned by this** ExecuteMethods(...)** method
        shall be as follows: **OK ** Requested methods were called; all, none,
        or some of them succeeded. **<anything else>** Problem, no method calls
        were attempted

        This method has id ``3.17``.

        - :cpp:expr:`TargetMembers`: Input parameter.


        - :cpp:expr:`TargetMethod`: Input parameter.


        - :cpp:expr:`InData`: Input parameter.


        - :cpp:expr:`Results`: Output parameter.


    .. _ocamatrix_executecommands:

    .. cpp:function:: OcaStatus ExecuteCommands(OcaList32<OcaMatrixCommand> Commands, OcaList32<OcaCommandResult> &Results)

        Execute various methods in various Matrix Members with individual
        parameter sets for each. Return the status and returned parameter
        values, if any, from each call. When an addressed Member is a Block,
        this method shall not be capable of executing methods of objects inside
        the Block. The **OcaStatus** value returned by this**
        ExecuteMethods(...)** method shall be as follows: **OK ** Requested
        methods were called; all, none, or some of them succeeded. **<anything
        else>** Problem, no method calls were attempted

        This method has id ``3.18``.

        - :cpp:expr:`Commands`: Input parameter.


        - :cpp:expr:`Results`: Output parameter.


    Methods inherited from :ref:`ocaworker`:

    - :ref:`OcaWorker::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaWorker::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaWorker::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaWorker::GetRole <ocaroot_getrole>`

    - :ref:`OcaWorker::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaWorker::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaWorker::Unlock <ocaroot_unlock>`

    - :ref:`OcaWorker::AddPort <ocaworker_addport>`

    - :ref:`OcaWorker::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaWorker::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaWorker::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaWorker::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaWorker::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaWorker::GetOwner <ocaworker_getowner>`

    - :ref:`OcaWorker::GetPath <ocaworker_getpath>`

    - :ref:`OcaWorker::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaWorker::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaWorker::GetPortName <ocaworker_getportname>`

    - :ref:`OcaWorker::GetPorts <ocaworker_getports>`

    - :ref:`OcaWorker::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaWorker::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaWorker::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaWorker::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaWorker::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaWorker::SetPortName <ocaworker_setportname>`

