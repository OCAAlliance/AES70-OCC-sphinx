.. _ocamatrix:

1.1.5  OcaMatrix
================

Class Hirarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaMatrix <ocamatrix>` 

.. cpp:class:: OcaMatrix: OcaWorker

    A matrix is a rectangular array of identical objects (" **members** ")
    that is coordinate addressable and has sets of common input and output
    ports. The matrix host does not instantiate these objects, but instead
    mediates the coordinate addressing, implements the common input and
    output ports, and provdes certain other aggregate functions. Matrix
    members may be workers (including blocks), or agents. All members of a
    matrix must be of the same class. No object may belong to more than
    one matrix at a time. No object may appear more than once in a given
    matrix. The complete model of an OCA matrix consists of: 1. One
    instance of **OcaMatrix.** 2. **(N x M) members** , where each member
    is an instance of a worker or agent class. For any given matrix, this
    class must be the same for all members, and is referred to as the
    **member class.** Members are sometimes referred to as **cells** of
    the matrix. 3. One additional instance of the member class, called the
    **matrix proxy.** Thus, the **OcaMatrix** instance is a container for
    the two-dimensional collection of its members. Once a matrix is set
    up, the controller may get and set member properties by the following
    procedures: **Get** To get a property value of member (x1, y1): 1.
    Controller calls **OcaMatrix.SetXY(x1, y1)** . This action: - locks
    the **OcaMatrix** instance, and - posts x1 and y1 as coordinates of
    the object whose property value is to be retrieved. 2. Controller
    calls the matrix proxy's **Get** method for the property value
    desired. This action causes the **OcaMatrix** instance to: - decode
    the posted x1 and y1 values into a member ONo. - call the given
    **Get** method for the object identified by the decoded ONo. -
    aggregate the **OcaResult** from each **Get** call into a consolidated
    **OcaResult** . - unlock the **OcaMatrix** instance. - return the
    consolidated **OcaResult** to the controller. **Set** To set a
    property value of member (x1, y1), or of row (0, y1) or column (x1, 0)
    or whole matrix (0,0) 1. Controller calls **OcaMatrix.SetXY(x1, y1)**
    . This action: - locks the **OcaMatrix** instance, and - posts x1 and
    y1 as coordinates of the object whose property value is to be changed.
    2. Controller calls the matrix proxy's **Set** method for the target
    property. This action causes the **OcaMatrix** instance to: - decode
    the posted x1 and y1 values into a list of target member ONos, as
    follows: If x1 :raw:html:`&gt;` 0 and y1 :raw:html:`&gt;` 0, the list
    will be the single ONo of the addressed cell. If x1 = 0 and y1
    :raw:html:`&gt;` 0, the list will be the list of ONos of the cells in
    row y1 . If x1 :raw:html:`&gt;` 0 and y1 = 0, the list will be the
    list of ONos of the cells in column x1. If x1 = 0 and y1 = 0, the list
    will be the list of ONos of all cells of the matrix. - call the given
    **Set** method for each target member in the ONo list. - aggregate the
    **OcaResult** from each **Set** call into a consolidated **OcaResult**
    . - unlock the **OcaMatrix** instance.

    **Properties**:

    .. _ocamatrix_classid:

    .. cpp:member:: OcaClassID ClassID

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``3.1``.

    .. _ocamatrix_classversion:

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

        This property has id ``3.2``.

    .. _ocamatrix_x:

    .. cpp:member:: OcaMatrixCoordinate X

        Active column index. The active column is the column to which matrix
        proxy method calls will be reflected. Value is zero-relative, i.e. the
        first column is number zero. A value of 65535 means all columns in the
        matrix.

        This property has id ``3.1``.

    .. _ocamatrix_y:

    .. cpp:member:: OcaMatrixCoordinate Y

        Active row index. The active row is the row to which matrix proxy
        changes will be reflected. Value is zero-relative, i.e. the first row
        is number zero. A value of 65535 means all rows in the matrix.

        This property has id ``3.2``.

    .. _ocamatrix_xsize:

    .. cpp:member:: OcaMatrixCoordinate xSize

        Number of columns in the matrix. Readonly in some cases.

        This property has id ``3.3``.

    .. _ocamatrix_ysize:

    .. cpp:member:: OcaMatrixCoordinate ySize

        Number of rows in the matrix. Readonly in some cases.

        This property has id ``3.4``.

    .. _ocamatrix_members:

    .. cpp:member:: OcaList2D<OcaONo> Members

        2D array of member object numbers.

        This property has id ``3.5``.

    .. _ocamatrix_proxy:

    .. cpp:member:: OcaONo Proxy

        Object number of the matrix proxy.

        This property has id ``3.6``.

    .. _ocamatrix_portsperrow:

    .. cpp:member:: OcaUint8 PortsPerRow

        Number of input ports per row- e.g. for a stereo matrix, the value
        would be 2.

        This property has id ``3.7``.

    .. _ocamatrix_portspercolumn:

    .. cpp:member:: OcaUint8 PortsPerColumn

        Number of output ports per column - e.g. for a stereo matrix, the
        value would be 2.

        This property has id ``3.8``.

    Properties inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <OcaWorker_Enabled>`
    
    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <OcaWorker_Ports>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <OcaWorker_Label>`
    
    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <OcaWorker_Owner>`
    
    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <OcaWorker_Latency>`
    
    
    Properties inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <OcaRoot_ObjectNumber>`
    
    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <OcaRoot_Lockable>`
    
    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <OcaRoot_Role>`
    
    

    **Methods**:

    .. _ocamatrix_getcurrentxy:

    .. cpp:function:: OcaStatus GetCurrentXY(OcaMatrixCoordinate &x, OcaMatrixCoordinate &y)

        Gets coordinates of the currently active area (cell, row, column, or
        whole matrix). The returned status indicates whether the operation was
        successful.

        This method has id ``3.1``.

        :param OcaMatrixCoordinate x: Output parameter.
        :param OcaMatrixCoordinate y: Output parameter.

    .. _ocamatrix_setcurrentxy:

    .. cpp:function:: OcaStatus SetCurrentXY(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        Sets the currently active area (cell, row, column, or whole matrix).
        The returned status indicates whether the operation was successful.

        This method has id ``3.2``.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.

    .. _ocamatrix_getsize:

    .. cpp:function:: OcaStatus GetSize(OcaMatrixCoordinate &xSize, OcaMatrixCoordinate &ySize, OcaMatrixCoordinate &minXSize, OcaMatrixCoordinate &maxXSize, OcaMatrixCoordinate &minYSize, OcaMatrixCoordinate &maxYSize)

        Gets the matrix size. The returned status indicates whether the
        operation was successful.

        This method has id ``3.3``.

        :param OcaMatrixCoordinate xSize: Output parameter.
        :param OcaMatrixCoordinate ySize: Output parameter.
        :param OcaMatrixCoordinate minXSize: Output parameter.
        :param OcaMatrixCoordinate maxXSize: Output parameter.
        :param OcaMatrixCoordinate minYSize: Output parameter.
        :param OcaMatrixCoordinate maxYSize: Output parameter.

    .. _ocamatrix_setsize:

    .. cpp:function:: OcaStatus SetSize(OcaMatrixCoordinate xSize, OcaMatrixCoordinate ySize)

        Sets the matrix size. The returned status indicates whether the
        operation was successful. This method will not be available for
        fixed-size matrices.

        This method has id ``3.4``.

        :param OcaMatrixCoordinate xSize: Input parameter.
        :param OcaMatrixCoordinate ySize: Input parameter.

    .. _ocamatrix_getmembers:

    .. cpp:function:: OcaStatus GetMembers(OcaList2D<OcaONo> &members)

        Retrieves the 2D array of member object numbers. Cells for which no
        member has been defined will return Zero as the object number.

        This method has id ``3.5``.

        :param OcaList2D<OcaONo> members: Output parameter.

    .. _ocamatrix_setmembers:

    .. cpp:function:: OcaStatus SetMembers(OcaList2D<OcaONo> members)

        Sets the entire 2D array of member object numbers. Row and column size
        of the **members** parameter must be equal to the current size of the
        matrix.

        This method has id ``3.6``.

        :param OcaList2D<OcaONo> members: Input parameter.

    .. _ocamatrix_getmember:

    .. cpp:function:: OcaStatus GetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo &memberONo)

        Retrieves the object number of the member at position (x,y). If no
        member is defined at this position, returns an object number value of
        Zero.

        This method has id ``3.7``.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.
        :param OcaONo memberONo: Output parameter.

    .. _ocamatrix_setmember:

    .. cpp:function:: OcaStatus SetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo memberONo)

        Installs a particular object as a member at position (x,y). If another
        object was at this position, it is removed.

        This method has id ``3.8``.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.
        :param OcaONo memberONo: Input parameter.

    .. _ocamatrix_getproxy:

    .. cpp:function:: OcaStatus GetProxy(OcaONo &ONo)

        Gets the object number of the matrix proxy.

        This method has id ``3.9``.

        :param OcaONo ONo: Output parameter.

    .. _ocamatrix_setproxy:

    .. cpp:function:: OcaStatus SetProxy(OcaONo ONo)

        Sets the object number of the matrix proxy.

        This method has id ``3.10``.

        :param OcaONo ONo: Input parameter.

    .. _ocamatrix_getportsperrow:

    .. cpp:function:: OcaStatus GetPortsPerRow(OcaUint8 &Ports)

        Gets the number of ports per row. These are input ports.

        This method has id ``3.11``.

        :param OcaUint8 Ports: Output parameter.

    .. _ocamatrix_setportsperrow:

    .. cpp:function:: OcaStatus SetPortsPerRow(OcaUint8 Ports)

        Sets the number of ports per row. These must be input ports.

        This method has id ``3.12``.

        :param OcaUint8 Ports: Input parameter.

    .. _ocamatrix_getportspercolumn:

    .. cpp:function:: OcaStatus GetPortsPerColumn(OcaUint8 &Ports)

        Gets the number of ports per output channel. These are output ports.

        This method has id ``3.13``.

        :param OcaUint8 Ports: Output parameter.

    .. _ocamatrix_setportspercolumn:

    .. cpp:function:: OcaStatus SetPortsPerColumn(OcaUint8 Ports)

        Sets the number of ports per column. These must be output ports.

        This method has id ``3.14``.

        :param OcaUint8 Ports: Input parameter.

    .. _ocamatrix_setcurrentxylock:

    .. cpp:function:: OcaStatus SetCurrentXYLock(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        Sets the currently active area (cell, row, column, or whole matrix)
        and locks it. Fails if the referenced members cannot all be locked.
        The returned status indicates whether the operation was successful.

        This method has id ``3.15``.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.

    .. _ocamatrix_unlockcurrent:

    .. cpp:function:: OcaStatus UnlockCurrent()

        Unlocks the currently active area of the matrix. Fails if all the
        members of the currently active area cannot be unlocked. Failure is
        _not_ triggered if one or more members of the currently active area
        are already unlocked at the time Unlock() is called. The returned
        status indicates whether the operation was successful.

        This method has id ``3.16``.



    Methods inherited from :ref:`OcaWorker <OcaWorker>`:
    
    - :ref:`OcaWorker::GetEnabled(enabled) <OcaWorker_GetEnabled>`
    
    - :ref:`OcaWorker::SetEnabled(enabled) <OcaWorker_SetEnabled>`
    
    - :ref:`OcaWorker::AddPort(Label, Mode, ID) <OcaWorker_AddPort>`
    
    - :ref:`OcaWorker::DeletePort(ID) <OcaWorker_DeletePort>`
    
    - :ref:`OcaWorker::GetPorts(OcaPorts) <OcaWorker_GetPorts>`
    
    - :ref:`OcaWorker::GetPortName(PortID, Name) <OcaWorker_GetPortName>`
    
    - :ref:`OcaWorker::SetPortName(PortID, Name) <OcaWorker_SetPortName>`
    
    - :ref:`OcaWorker::GetLabel(label) <OcaWorker_GetLabel>`
    
    - :ref:`OcaWorker::SetLabel(label) <OcaWorker_SetLabel>`
    
    - :ref:`OcaWorker::GetOwner(owner) <OcaWorker_GetOwner>`
    
    - :ref:`OcaWorker::GetLatency(latency) <OcaWorker_GetLatency>`
    
    - :ref:`OcaWorker::SetLatency(latency) <OcaWorker_SetLatency>`
    
    - :ref:`OcaWorker::GetPath(NamePath, ONoPath) <OcaWorker_GetPath>`
    
    
    Methods inherited from :ref:`OcaRoot <OcaRoot>`:
    
    - :ref:`OcaRoot::GetClassIdentification(ClassIdentification) <OcaRoot_GetClassIdentification>`
    
    - :ref:`OcaRoot::GetLockable(lockable) <OcaRoot_GetLockable>`
    
    - :ref:`OcaRoot::LockTotal() <OcaRoot_LockTotal>`
    
    - :ref:`OcaRoot::Unlock() <OcaRoot_Unlock>`
    
    - :ref:`OcaRoot::GetRole(Role) <OcaRoot_GetRole>`
    
    - :ref:`OcaRoot::LockReadonly() <OcaRoot_LockReadonly>`
    
    


