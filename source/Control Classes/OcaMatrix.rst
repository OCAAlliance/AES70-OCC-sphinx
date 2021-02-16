.. _ocamatrix:

1.1.5  OcaMatrix
================

Extends :ref:`OcaWorker <ocaworker>`.

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
    follows: If x1 &gt; 0 and y1 &gt; 0, the list will be the single ONo
    of the addressed cell. If x1 = 0 and y1 &gt; 0, the list will be the
    list of ONos of the cells in row y1 . If x1 &gt; 0 and y1 = 0, the
    list will be the list of ONos of the cells in column x1. If x1 = 0 and
    y1 = 0, the list will be the list of ONos of all cells of the matrix.
    - call the given **Set** method for each target member in the ONo
    list. - aggregate the **OcaResult** from each **Set** call into a
    consolidated **OcaResult** . - unlock the **OcaMatrix** instance.

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.1``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.2``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaMatrixCoordinate X

        This property has id ``3.1``.

        Active column index. The active column is the column to which matrix
        proxy method calls will be reflected. Value is zero-relative, i.e. the
        first column is number zero. A value of 65535 means all columns in the
        matrix.

    .. cpp:member:: OcaMatrixCoordinate Y

        This property has id ``3.2``.

        Active row index. The active row is the row to which matrix proxy
        changes will be reflected. Value is zero-relative, i.e. the first row
        is number zero. A value of 65535 means all rows in the matrix.

    .. cpp:member:: OcaMatrixCoordinate xSize

        This property has id ``3.3``.

        Number of columns in the matrix. Readonly in some cases.

    .. cpp:member:: OcaMatrixCoordinate ySize

        This property has id ``3.4``.

        Number of rows in the matrix. Readonly in some cases.

    .. cpp:member:: OcaList2D<OcaONo> Members

        This property has id ``3.5``.

        2D array of member object numbers.

    .. cpp:member:: OcaONo Proxy

        This property has id ``3.6``.

        Object number of the matrix proxy.

    .. cpp:member:: OcaUint8 PortsPerRow

        This property has id ``3.7``.

        Number of input ports per row- e.g. for a stereo matrix, the value
        would be 2.

    .. cpp:member:: OcaUint8 PortsPerColumn

        This property has id ``3.8``.

        Number of output ports per column - e.g. for a stereo matrix, the
        value would be 2.

    .. cpp:function:: OcaStatus GetCurrentXY(OcaMatrixCoordinate &x, OcaMatrixCoordinate &y)

        This method has id ``3.1``.

        Gets coordinates of the currently active area (cell, row, column, or
        whole matrix). The returned status indicates whether the operation was
        successful.

        :param OcaMatrixCoordinate x: Output parameter.
        :param OcaMatrixCoordinate y: Output parameter.

    .. cpp:function:: OcaStatus SetCurrentXY(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        This method has id ``3.2``.

        Sets the currently active area (cell, row, column, or whole matrix).
        The returned status indicates whether the operation was successful.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.

    .. cpp:function:: OcaStatus GetSize(OcaMatrixCoordinate &xSize, OcaMatrixCoordinate &ySize, OcaMatrixCoordinate &minXSize, OcaMatrixCoordinate &maxXSize, OcaMatrixCoordinate &minYSize, OcaMatrixCoordinate &maxYSize)

        This method has id ``3.3``.

        Gets the matrix size. The returned status indicates whether the
        operation was successful.

        :param OcaMatrixCoordinate xSize: Output parameter.
        :param OcaMatrixCoordinate ySize: Output parameter.
        :param OcaMatrixCoordinate minXSize: Output parameter.
        :param OcaMatrixCoordinate maxXSize: Output parameter.
        :param OcaMatrixCoordinate minYSize: Output parameter.
        :param OcaMatrixCoordinate maxYSize: Output parameter.

    .. cpp:function:: OcaStatus SetSize(OcaMatrixCoordinate xSize, OcaMatrixCoordinate ySize)

        This method has id ``3.4``.

        Sets the matrix size. The returned status indicates whether the
        operation was successful. This method will not be available for
        fixed-size matrices.

        :param OcaMatrixCoordinate xSize: Input parameter.
        :param OcaMatrixCoordinate ySize: Input parameter.

    .. cpp:function:: OcaStatus GetMembers(OcaList2D<OcaONo> &members)

        This method has id ``3.5``.

        Retrieves the 2D array of member object numbers. Cells for which no
        member has been defined will return Zero as the object number.

        :param OcaList2D<OcaONo> members: Output parameter.

    .. cpp:function:: OcaStatus SetMembers(OcaList2D<OcaONo> members)

        This method has id ``3.6``.

        Sets the entire 2D array of member object numbers. Row and column size
        of the **members** parameter must be equal to the current size of the
        matrix.

        :param OcaList2D<OcaONo> members: Input parameter.

    .. cpp:function:: OcaStatus GetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo &memberONo)

        This method has id ``3.7``.

        Retrieves the object number of the member at position (x,y). If no
        member is defined at this position, returns an object number value of
        Zero.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.
        :param OcaONo memberONo: Output parameter.

    .. cpp:function:: OcaStatus SetMember(OcaMatrixCoordinate x, OcaMatrixCoordinate y, OcaONo memberONo)

        This method has id ``3.8``.

        Installs a particular object as a member at position (x,y). If another
        object was at this position, it is removed.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.
        :param OcaONo memberONo: Input parameter.

    .. cpp:function:: OcaStatus GetProxy(OcaONo &ONo)

        This method has id ``3.9``.

        Gets the object number of the matrix proxy.

        :param OcaONo ONo: Output parameter.

    .. cpp:function:: OcaStatus SetProxy(OcaONo ONo)

        This method has id ``3.10``.

        Sets the object number of the matrix proxy.

        :param OcaONo ONo: Input parameter.

    .. cpp:function:: OcaStatus GetPortsPerRow(OcaUint8 &Ports)

        This method has id ``3.11``.

        Gets the number of ports per row. These are input ports.

        :param OcaUint8 Ports: Output parameter.

    .. cpp:function:: OcaStatus SetPortsPerRow(OcaUint8 Ports)

        This method has id ``3.12``.

        Sets the number of ports per row. These must be input ports.

        :param OcaUint8 Ports: Input parameter.

    .. cpp:function:: OcaStatus GetPortsPerColumn(OcaUint8 &Ports)

        This method has id ``3.13``.

        Gets the number of ports per output channel. These are output ports.

        :param OcaUint8 Ports: Output parameter.

    .. cpp:function:: OcaStatus SetPortsPerColumn(OcaUint8 Ports)

        This method has id ``3.14``.

        Sets the number of ports per column. These must be output ports.

        :param OcaUint8 Ports: Input parameter.

    .. cpp:function:: OcaStatus SetCurrentXYLock(OcaMatrixCoordinate x, OcaMatrixCoordinate y)

        This method has id ``3.15``.

        Sets the currently active area (cell, row, column, or whole matrix)
        and locks it. Fails if the referenced members cannot all be locked.
        The returned status indicates whether the operation was successful.

        :param OcaMatrixCoordinate x: Input parameter.
        :param OcaMatrixCoordinate y: Input parameter.

    .. cpp:function:: OcaStatus UnlockCurrent()

        This method has id ``3.16``.

        Unlocks the currently active area of the matrix. Fails if all the
        members of the currently active area cannot be unlocked. Failure is
        _not_ triggered if one or more members of the currently active area
        are already unlocked at the time Unlock() is called. The returned
        status indicates whether the operation was successful.


