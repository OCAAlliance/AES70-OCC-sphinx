.. _ocadynamicscurve:

1.1.1.16  OcaDynamicsCurve
==========================

Extends :ref:`OcaActuator <ocaactuator>`.

.. cpp:class:: OcaDynamicsCurve: OcaActuator

    Dynamic compression / expansion curve. **Curve** means a function that
    expresses the relationship of output level to input level. The
    dependent variable (Y) of the curve is output level; the independent
    variable (X) is input level. Every curve is composed of **(n+1)**
    straight-line **segments** joined by **(n)** small fillets called
    **knees** . Each knee occurs at a particular input level value called
    the **threshold.** Each segment is characterized by its **slope.** | /
    | S3 / | S2 / | T1 **-------------** T2 | / | S1 / | / | /
    +------------------------------------ This "drawing" shows a
    three-segment curve. The horizontal axis is input level, vertical axis
    is output level. Algebraically, a curve is a function **Out = Curve(
    In, T[1..n-1], S[1..n], K[1..n-1] )** where **n** is the number of
    segments, and **In** is input level in dBr **Out** is output level in
    dBr **T[1...n-1]** is an array of **thresholds** in dBr **S[1...n]**
    is an array of **slopes** in dBr per dBr, i.e. unitless **K[1..n]** is
    the **knee parameter** , an implementation-dependant parameter that
    specifies the shape of the curve around the knee. Each segment has a
    slope that expresses its ratio of output level to input level. Note
    that this slope is the inverse of what dynamics processors call
    "ratio". For example, a ratio of 2:1 is represented by a curve segment
    with slope 1/2 = 0.5. This model can represent familiar audio dynamics
    elements (we ignore **K[]** in these examples): - Compressor with
    ratio of 2:1 and threshold of 10dBr: **n = 2** **T[1] = 10** **S[1] =
    1** **S[2] = 0.5** - Hard limiter with threshold of 18dBr: **n = 2**
    T[1] = 18 S[1] = 1 S[2] = 0 - Upward expander with ratio of 1.5:1 and
    threshold of -12dBr: **n = 2** T[1] = -12 S[1] = 1 S[2] = 1.5 -
    Downward expander (gate) with ratio of 50:1 and threshold of -45dBr:
    **n = 2** T[1] = -45 S[1] = 50 S[2] = 1 This class,
    **OcaDynamicsCurve,** adds two additional parameters to the basic
    curve mechanism. **Out = Curve( In, T[1..n-1], S[1..n], K[1..n-1] ,
    Floor, Ceiling)** where **In, T[], and S[],** and **K[]** are as
    defined above. **Floor** is the lowest gain (in dBr) that the dynamics
    element is allowed to produce. **Ceiling** is the highest gain (in
    dBr) that the dynamics element is allowed to produce. To show the use
    of **Floor** and **Ceiling** , we revisit some of the examples above
    (again, **K[]** is ignored): - Compressor with ratio of 2:1, threshold
    of 10dBr, and max gain reduction of 20dB: **n = 2** **T[1] = 10**
    **S[1] = 1** **S[2] = 0.5** **Floor = -20** **Ceiling = 0** - Upward
    expander with ratio of 1.5:1, threshold of -12dBr, and max gain boost
    of 4dB: **n = 2** T[1] = -12 S[1] = 1 S[2] = 1.5 Floor = 0 Ceiling =
    4.0 More complex dynamics curves can be modeled by using more segments
    ( **n &gt; 2)** .

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

    .. cpp:member:: OcaUint8 NSegments

        This property has id ``4.1``.

        Number of curve segments.

    .. cpp:member:: OcaList<OcaDBr> Threshold

        This property has id ``4.2``.

        **T[1..n-1]** . See class description for details.

    .. cpp:member:: OcaList<OcaFloat32> Slope

        This property has id ``4.3``.

        **S[1..n]** . See class description for details.

    .. cpp:member:: OcaList<OcaFloat32> KneeParameter

        This property has id ``4.4``.

        **K[1..n]** . See class description for details.

    .. cpp:member:: OcaDB DynamicGainFloor

        This property has id ``4.5``.

        Lowest allowed dynamic gain value. See class description for details.

    .. cpp:member:: OcaDB DynamicGainCeiling

        This property has id ``4.6``.

        Highest allowed dynamic gain value. See class description for details.

    .. cpp:function:: OcaStatus GetNSegments(OcaUint8 &n, OcaUint8 &minN, OcaUint8 &maxN)

        This method has id ``4.1``.

        Gets the number of curve segments. The return value indicates whether
        the value was successfully retrieved.

        :param OcaUint8 n: Output parameter.
        :param OcaUint8 minN: Output parameter.
        :param OcaUint8 maxN: Output parameter.

    .. cpp:function:: OcaStatus SetNSegments(OcaUint8 Slope)

        This method has id ``4.2``.

        Sets the number of curve segments. The return value indicates whether
        the data was successfully set. If this method increases the value of
        n, the data in properties **Threshold** , **Slope** , and
        **KneeParameter** of the new segment are by default set to the values
        of the previous segment.

        :param OcaUint8 Slope: Input parameter.

    .. cpp:function:: OcaStatus GetThreshold(OcaList<OcaDBr> &Threshold, OcaDBz &minThreshold, OcaDBz &maxThreshold)

        This method has id ``4.3``.

        Gets the list of Threshold values. The return value indicates whether
        the data was successfully retrieved.

        :param OcaList<OcaDBr> Threshold: Output parameter.
        :param OcaDBz minThreshold: Output parameter.
        :param OcaDBz maxThreshold: Output parameter.

    .. cpp:function:: OcaStatus SetThreshold(OcaList<OcaDBr> Threshold)

        This method has id ``4.4``.

        Sets the list of Threshold values. The return value indicates whether
        the values were successfully set.

        :param OcaList<OcaDBr> Threshold: Input parameter.

    .. cpp:function:: OcaStatus GetSlope(OcaList<OcaFloat32> &slope, OcaList<OcaFloat32> &minSlope, OcaList<OcaFloat32> &maxSlope)

        This method has id ``4.5``.

        Gets the list of Slope values. The return value indicates whether the
        list was successfully retrieved.

        :param OcaList<OcaFloat32> slope: Output parameter.
        :param OcaList<OcaFloat32> minSlope: Output parameter.
        :param OcaList<OcaFloat32> maxSlope: Output parameter.

    .. cpp:function:: OcaStatus SetSlope(OcaList<OcaFloat32> slope)

        This method has id ``4.6``.

        Sets the list of Slope values. The return value indicates whether the
        values were successfully set.

        :param OcaList<OcaFloat32> slope: Input parameter.

    .. cpp:function:: OcaStatus GetKneeParameter(OcaList<OcaFloat32> &parameter, OcaList<OcaFloat32> &minParameter, OcaList<OcaFloat32> &maxParameter)

        This method has id ``4.7``.

        Gets the list of KneeParameter valuess. The return value indicates
        whether the list was successfully retrieved.

        :param OcaList<OcaFloat32> parameter: Output parameter.
        :param OcaList<OcaFloat32> minParameter: Output parameter.
        :param OcaList<OcaFloat32> maxParameter: Output parameter.

    .. cpp:function:: OcaStatus SetKneeParameter(OcaList<OcaFloat32> parameter)

        This method has id ``4.8``.

        Sets the list of KneeParameter values. The return value indicates
        whether the values were successfully set.

        :param OcaList<OcaFloat32> parameter: Input parameter.

    .. cpp:function:: OcaStatus GetDynamicGainCeiling(OcaDB &gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``4.9``.

        Gets the value of the DynamicGainCeiling property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaDB gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. cpp:function:: OcaStatus SetDynamicGainCeiling(OcaDB gain)

        This method has id ``4.10``.

        Sets the value of the DynamicGainCeiling property. The return value
        indicates whether the data was successfully set.

        :param OcaDB gain: Input parameter.

    .. cpp:function:: OcaStatus GetDynamicGainFloor(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        This method has id ``4.11``.

        Gets the value of the DynamicGainFloor property. The return value
        indicates whether the data was successfully retrieved.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. cpp:function:: OcaStatus SetDynamicGainFloor(OcaDB Gain)

        This method has id ``4.12``.

        Sets the value of the DynamicGainFloor property. The return value
        indicates whether the data was successfully set.

        :param OcaDB Gain: Input parameter.

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaUint8 nSegments, OcaList<OcaDBr> Threshold[], OcaList<OcaFloat32> Slope[], OcaList<OcaFloat32> KneeParameter[], OcaDB DynamicGainFloor, OcaDB DynamicGainCeiling)

        This method has id ``4.13``.

        Sets some or all dynamics curve parameters. The return value indicates
        if the parameters were successfully set. The action of this method is
        atomic - if any of the value changes fails, none of the changes are
        made.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaUint8 nSegments: Input parameter.
        :param OcaList<OcaDBr> Threshold[]: Input parameter.
        :param OcaList<OcaFloat32> Slope[]: Input parameter.
        :param OcaList<OcaFloat32> KneeParameter[]: Input parameter.
        :param OcaDB DynamicGainFloor: Input parameter.
        :param OcaDB DynamicGainCeiling: Input parameter.

