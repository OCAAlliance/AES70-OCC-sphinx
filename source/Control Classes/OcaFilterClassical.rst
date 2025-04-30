.. _ocafilterclassical:

1.1.1.9  OcaFilterClassical
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaFilterClassical <ocafilterclassical>`

.. cpp:class:: OcaFilterClassical: OcaActuator

    A classical analog-style filter - highpass, lowpass, bandpass, etc., with
    shape characteristics such as Butterworth, Chebyshev, Bessel, and
    Linkwitz-Riley. Frequently used in loudspeaker crossover networks.

    **Properties**:


    .. _ocafilterclassical_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.9"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocafilterclassical_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocafilterclassical_frequency:

    .. cpp:member:: OcaFrequency Frequency

        The frequency of the filter.

        This property has id ``4.1``.

    .. _ocafilterclassical_passband:

    .. cpp:member:: OcaFilterPassband Passband

        Lowpass, highpass, bandpass, bandreject

        This property has id ``4.2``.

    .. _ocafilterclassical_shape:

    .. cpp:member:: OcaClassicalFilterShape Shape

        Shape family - Butterworth, Bessell, etc.

        This property has id ``4.3``.

    .. _ocafilterclassical_order:

    .. cpp:member:: OcaUint16 Order

        Filter order

        This property has id ``4.4``.

    .. _ocafilterclassical_parameter:

    .. cpp:member:: OcaFloat32 Parameter

        Ripple or other filter parameter, depending on shape. Not used by some
        shapes.

        This property has id ``4.5``.

    Properties inherited from :ref:`ocaactuator`:

    - :cpp:texpr:`OcaClassID` :ref:`OcaRoot::ClassID <ocaroot_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaRoot::ClassVersion <ocaroot_classversion>`

    - :cpp:texpr:`OcaONo` :ref:`OcaRoot::ObjectNumber <ocaroot_objectnumber>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaRoot::Lockable <ocaroot_lockable>`

    - :cpp:texpr:`OcaString` :ref:`OcaRoot::Role <ocaroot_role>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaWorker::ClassID <ocaworker_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaWorker::ClassVersion <ocaworker_classversion>`

    - :cpp:texpr:`OcaBoolean` :ref:`OcaWorker::Enabled <ocaworker_enabled>`

    - :cpp:texpr:`OcaList<OcaPort>` :ref:`OcaWorker::Ports <ocaworker_ports>`

    - :cpp:texpr:`OcaString` :ref:`OcaWorker::Label <ocaworker_label>`

    - :cpp:texpr:`OcaONo` :ref:`OcaWorker::Owner <ocaworker_owner>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaWorker::Latency <ocaworker_latency>`

    - :cpp:texpr:`OcaClassID` :ref:`OcaActuator::ClassID <ocaactuator_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaActuator::ClassVersion <ocaactuator_classversion>`


    **Methods**:


    .. _ocafilterclassical_getfrequency:

    .. cpp:function:: OcaStatus GetFrequency(OcaFrequency &Frequency, OcaFrequency &minFrequency, OcaFrequency &maxFrequency)

        Gets the value of the Frequency property. The return value indicates if
        the property was successfully retrieved.

        This method has id ``4.1``.

        - :cpp:expr:`Frequency`: Output parameter.


        - :cpp:expr:`minFrequency`: Output parameter.


        - :cpp:expr:`maxFrequency`: Output parameter.


    .. _ocafilterclassical_setfrequency:

    .. cpp:function:: OcaStatus SetFrequency(OcaFrequency frequency)

        Sets the value of the Frequency property. The return value indicates if
        the property was successfully set.

        This method has id ``4.2``.

        - :cpp:expr:`frequency`: Input parameter.


    .. _ocafilterclassical_getpassband:

    .. cpp:function:: OcaStatus GetPassband(OcaFilterPassband &Passband)

        Returns the passband specification of the filter object. The return
        value indicates if the specification was successfully retrieved.

        This method has id ``4.3``.

        - :cpp:expr:`Passband`: Output parameter.


    .. _ocafilterclassical_setpassband:

    .. cpp:function:: OcaStatus SetPassband(OcaFilterPassband Passband)

        Sets the passband specification of the filter object. The return value
        indicates if the specification was successfully set.

        This method has id ``4.4``.

        - :cpp:expr:`Passband`: Input parameter.


    .. _ocafilterclassical_getshape:

    .. cpp:function:: OcaStatus GetShape(OcaClassicalFilterShape &Shape)

        Returns the Shape property of the filter. The return value indicates if
        the property was successfully retrieved.

        This method has id ``4.5``.

        - :cpp:expr:`Shape`: Output parameter.


    .. _ocafilterclassical_setshape:

    .. cpp:function:: OcaStatus SetShape(OcaClassicalFilterShape Shape)

        Sets the Shape property of the filter. The return value indicates if the
        property was successfully set.

        This method has id ``4.6``.

        - :cpp:expr:`Shape`: Input parameter.


    .. _ocafilterclassical_getorder:

    .. cpp:function:: OcaStatus GetOrder(OcaUint16 &Order, OcaUint16 &minOrder, OcaUint16 &maxOrder)

        Returns the order of the filter. The return value indicates if the
        property was successfully retrieved.

        This method has id ``4.7``.

        - :cpp:expr:`Order`: Output parameter.


        - :cpp:expr:`minOrder`: Output parameter.


        - :cpp:expr:`maxOrder`: Output parameter.


    .. _ocafilterclassical_setorder:

    .. cpp:function:: OcaStatus SetOrder(OcaUint16 Order)

        Sets the order of the filter. The return value indicates if the property
        was successfully set.

        This method has id ``4.8``.

        - :cpp:expr:`Order`: Input parameter.


    .. _ocafilterclassical_getparameter:

    .. cpp:function:: OcaStatus GetParameter(OcaFloat32 &Parameter, OcaFloat32 &minParameter, OcaFloat32 &maxParameter)

        Returns the filter parameter. The return value indicates if the property
        was successfully retrieved.

        This method has id ``4.9``.

        - :cpp:expr:`Parameter`: Output parameter.


        - :cpp:expr:`minParameter`: Output parameter.


        - :cpp:expr:`maxParameter`: Output parameter.


    .. _ocafilterclassical_setparameter:

    .. cpp:function:: OcaStatus SetParameter(OcaFloat32 Parameter)

        Sets the filter parameter. The return value indicates if the parameter
        was successfully set.

        This method has id ``4.10``.

        - :cpp:expr:`Parameter`: Input parameter.


    .. _ocafilterclassical_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaFrequency Frequency, OcaFilterPassband Passband, OcaClassicalFilterShape Shape, OcaUint16 Order, OcaFloat32 Parameter)

        Sets some or all filter parameter. The return value indicates if the
        parameters were successfully set. The action of this method is atomic -
        if any of the value changes fails, none of the changes are made.

        This method has id ``4.11``.

        - :cpp:expr:`Mask`: Input parameter.


        - :cpp:expr:`Frequency`: Input parameter.


        - :cpp:expr:`Passband`: Input parameter.


        - :cpp:expr:`Shape`: Input parameter.


        - :cpp:expr:`Order`: Input parameter.


        - :cpp:expr:`Parameter`: Input parameter.


    Methods inherited from :ref:`ocaactuator`:

    - :ref:`OcaActuator::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaActuator::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaActuator::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaActuator::Unlock <ocaroot_unlock>`

    - :ref:`OcaActuator::GetRole <ocaroot_getrole>`

    - :ref:`OcaActuator::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaActuator::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaActuator::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaActuator::AddPort <ocaworker_addport>`

    - :ref:`OcaActuator::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaActuator::GetPorts <ocaworker_getports>`

    - :ref:`OcaActuator::GetPortName <ocaworker_getportname>`

    - :ref:`OcaActuator::SetPortName <ocaworker_setportname>`

    - :ref:`OcaActuator::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaActuator::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaActuator::GetOwner <ocaworker_getowner>`

    - :ref:`OcaActuator::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaActuator::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaActuator::GetPath <ocaworker_getpath>`

