.. _ocafilterparametric:

1.1.1.10  OcaFilterParametric
=============================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaFilterParametric <ocafilterparametric>`

.. cpp:class:: OcaFilterParametric: OcaActuator

    Parametric equalizer section with various shape options.

    **Properties**:


    .. _ocafilterparametric_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.10"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocafilterparametric_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 3

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocafilterparametric_frequency:

    .. cpp:member:: OcaFrequency Frequency

        Frequency setpoint of the parametric filter.

        This property has id ``4.1``.

    .. _ocafilterparametric_inbandgain:

    .. cpp:member:: OcaDB InBandGain

        In-band gain of the parametric filter.

        This property has id ``4.4``.

    .. _ocafilterparametric_shape:

    .. cpp:member:: OcaParametricEQShape Shape

        Shape of the parametric filter - peak, shelf, etc.

        This property has id ``4.2``.

    .. _ocafilterparametric_shapeparameter:

    .. cpp:member:: OcaFloat32 ShapeParameter

        Width parameter. For certain filter types, this parameter may be used to
        represent extra information about the shape of the transfer function.

        This property has id ``4.5``.

    .. _ocafilterparametric_widthparameter:

    .. cpp:member:: OcaFloat32 WidthParameter

        Width parameter. For normal parametric implementations, this is the Q of
        the filter.

        This property has id ``4.3``.

    Properties inherited from :ref:`ocaactuator`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocafilterparametric_getfrequency:

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value and limits of the **Frequency** property.

        This method has id ``4.1``.

        - :cpp:expr:`Frequency`: Output parameter.


        - :cpp:expr:`minFrequency`: Output parameter.


        - :cpp:expr:`maxFrequency`: Output parameter.


    .. _ocafilterparametric_setfrequency:

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency Frequency)

        Sets the value of the **Frequency** property.

        This method has id ``4.2``.

        - :cpp:expr:`Frequency`: Input parameter.


    .. _ocafilterparametric_getshape:

    .. cpp:function:: OcaStatus GetShape(OcaParametricEQShape &type)

        Gets the value of the **Shape** property.

        This method has id ``4.3``.

        - :cpp:expr:`type`: Output parameter.


    .. _ocafilterparametric_setshape:

    .. cpp:function:: OcaStatus SetShape(OcaParametricEQShape type)

        Sets the value of the **Shape** property.

        This method has id ``4.4``.

        - :cpp:expr:`type`: Input parameter.


    .. _ocafilterparametric_getwidthparameter:

    .. cpp:function:: OcaStatus GetWidthParameter(OcaFloat32 &Width, OcaFloat32 &minWidth, OcaFloat32 &maxWidth)

        Gets the value and limits of the **WidthParameter** property.

        This method has id ``4.5``.

        - :cpp:expr:`Width`: Output parameter.


        - :cpp:expr:`minWidth`: Output parameter.


        - :cpp:expr:`maxWidth`: Output parameter.


    .. _ocafilterparametric_setwidthparameter:

    .. cpp:function:: OcaStatus SetWidthParameter(OcaFloat32 Width)

        Sets the value of the **WidthParameter** property.

        This method has id ``4.6``.

        - :cpp:expr:`Width`: Input parameter.


    .. _ocafilterparametric_getinbandgain:

    .. cpp:function:: OcaStatus GetInbandGain(OcaDB &gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the value, min, and max of the **InBandGain** property.

        This method has id ``4.7``.

        - :cpp:expr:`gain`: Output parameter.


        - :cpp:expr:`minGain`: Output parameter.


        - :cpp:expr:`maxGain`: Output parameter.


    .. _ocafilterparametric_setinbandgain:

    .. cpp:function:: OcaStatus SetInbandGain(OcaDB gain)

        Sets the value of the **InBandGain** property.

        This method has id ``4.8``.

        - :cpp:expr:`gain`: Input parameter.


    .. _ocafilterparametric_getshapeparameter:

    .. cpp:function:: OcaStatus GetShapeParameter(OcaFloat32 &shape, OcaFloat32 &minShape, OcaFloat32 &maxShape)

        Gets the value and limits of the **ShapeParameter** property.

        This method has id ``4.9``.

        - :cpp:expr:`shape`: Output parameter.


        - :cpp:expr:`minShape`: Output parameter.


        - :cpp:expr:`maxShape`: Output parameter.


    .. _ocafilterparametric_setshapeparameter:

    .. cpp:function:: OcaStatus SetShapeParameter(OcaFloat32 shape)

        Sets the value of the S**hapeParameter** property.

        This method has id ``4.10``.

        - :cpp:expr:`shape`: Input parameter.


    .. _ocafilterparametric_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaParametricEQShape Shape, OcaFloat32 WidthParameter, OcaDB InBandGain, OcaFloat32 ShapeParameter)

        Sets some or all filter parameters. The action of this method is atomic
        - if any of the value changes fails, none of the changes are made.

        This method has id ``4.11``.

        - :cpp:expr:`Mask`: Input parameter.


        - :cpp:expr:`Frequency`: Input parameter.


        - :cpp:expr:`Shape`: Input parameter.


        - :cpp:expr:`WidthParameter`: Input parameter.


        - :cpp:expr:`InBandGain`: Input parameter.


        - :cpp:expr:`ShapeParameter`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::GetLockState <ocaroot_getlockstate>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::SetLockNoWrite <ocaroot_setlocknowrite>`

    - :ref:`OcaActuator::SetLockNoReadWrite <ocaroot_setlocknoreadwrite>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::DeletePortClockMapEntry <ocaworker_deleteportclockmapentry>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

    - :ref:`OcaActuator::GetPortClockMap <ocaworker_getportclockmap>`

    - :ref:`OcaActuator::GetPortClockMapEntry <ocaworker_getportclockmapentry>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::SetPortClockMap <ocaworker_setportclockmap>`

    - :ref:`OcaActuator::SetPortClockMapEntry <ocaworker_setportclockmapentry>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

