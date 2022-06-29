.. _ocadynamicscurve:

1.1.1.16  OcaDynamicsCurve
==========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` :raw:html:`&rarr;` :ref:`OcaWorker <ocaworker>` :raw:html:`&rarr;` :ref:`OcaActuator <ocaactuator>` :raw:html:`&rarr;` :ref:`OcaDynamicsCurve <ocadynamicscurve>` 

.. cpp:class:: OcaDynamicsCurve: OcaActuator

    Dynamic compression / expansion curve.  **Curve**  means a function that expresses the relationship of output level to input level. The dependent variable (Y) of the curve is output level; the independent variable (X) is input level. Every curve is composed of  **(n+1)**  straight-line  **segments**  joined by  **(n)**  small fillets called  **knees** . Each knee occurs at a particular input level value called the  **threshold.**  Each segment is characterized by its  **slope.**   |    /    | S3    /    | S2    /    | T1 **-------------** T2 |    /    | S1    /    |    /    |    /    +------------------------------------ This "drawing" shows a three-segment curve. The horizontal axis is input level, vertical axis is output level. Algebraically, a curve is a function  **Out = Curve( In, T[1..n-1], S[1..n], K[1..n-1] )**  where  **n**  is the number of segments, and  **In** is input level in dBr  **Out** is output level in dBr  **T[1...n-1]**  is an array of  **thresholds**  in dBr  **S[1...n]** is an array of  **slopes**  in dBr per dBr, i.e. unitless  **K[1..n]**  is the  **knee parameter** , an implementation-dependant parameter that specifies the shape of the curve around the knee. Each segment has a slope that expresses its ratio of output level to input level. Note that this slope is the inverse of what dynamics processors call "ratio". For example, a ratio of 2:1 is represented by a curve segment with slope 1/2 = 0.5. This model can represent familiar audio dynamics elements (we ignore  **K[]**  in these examples): - Compressor with ratio of 2:1 and threshold of 10dBr:  **n = 2**   **T[1] = 10**   **S[1] = 1**   **S[2] = 0.5**  - Hard limiter with threshold of 18dBr:  **n = 2**  T[1] = 18 S[1] = 1 S[2] = 0 - Upward expander with ratio of 1.5:1 and threshold of -12dBr:  **n = 2**  T[1] = -12 S[1] = 1 S[2] = 1.5 - Downward expander (gate) with ratio of 50:1 and threshold of -45dBr:  **n = 2**  T[1] = -45 S[1] = 50 S[2] = 1 This class,  **OcaDynamicsCurve,**  adds two additional parameters to the basic curve mechanism.  **Out = Curve( In, T[1..n-1], S[1..n], K[1..n-1] , Floor, Ceiling)**  where  **In, T[], and S[],** and  **K[]**  are as defined above.  **Floor**  is the lowest gain (in dBr) that the dynamics element is allowed to produce.  **Ceiling** is the highest gain (in dBr) that the dynamics element is allowed to produce. To show the use of  **Floor**  and  **Ceiling** , we revisit some of the examples above (again,  **K[]**  is ignored): - Compressor with ratio of 2:1, threshold of 10dBr, and max gain reduction of 20dB:  **n = 2**   **T[1] = 10**   **S[1] = 1**   **S[2] = 0.5**   **Floor = -20**   **Ceiling = 0**  - Upward expander with ratio of 1.5:1, threshold of -12dBr, and max gain boost of 4dB:  **n = 2**  T[1] = -12 S[1] = 1 S[2] = 1.5 Floor = 0 Ceiling = 4.0 More complex dynamics curves can be modeled by using more segments ( **n &gt; 2)** .

    **Properties**:

    .. _ocadynamicscurve_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.16"

        Number that uniquely identifies the class. Note that this differs from the object number, which identifies the instantiated object. This property is an override of the  **OcaRoot** property.

        This property has id ``4.1``.

    .. _ocadynamicscurve_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class definition leads to a higher class version. This property is an override of the  **OcaRoot** property.

        This property has id ``4.2``.

    .. _ocadynamicscurve_nsegments:

    .. cpp:member:: OcaUint8 NSegments

        Number of curve segments.

        This property has id ``4.1``.

    .. _ocadynamicscurve_threshold:

    .. cpp:member:: OcaList<OcaDBr> Threshold

         **T[1..n-1]** . See class description for details.

        This property has id ``4.2``.

    .. _ocadynamicscurve_slope:

    .. cpp:member:: OcaList<OcaFloat32> Slope

         **S[1..n]** . See class description for details.

        This property has id ``4.3``.

    .. _ocadynamicscurve_kneeparameter:

    .. cpp:member:: OcaList<OcaFloat32> KneeParameter

         **K[1..n]** . See class description for details.

        This property has id ``4.4``.

    .. _ocadynamicscurve_dynamicgainfloor:

    .. cpp:member:: OcaDB DynamicGainFloor

        Lowest allowed dynamic gain value. See class description for details.

        This property has id ``4.5``.

    .. _ocadynamicscurve_dynamicgainceiling:

    .. cpp:member:: OcaDB DynamicGainCeiling

        Highest allowed dynamic gain value. See class description for details.

        This property has id ``4.6``.

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

    .. _ocadynamicscurve_getnsegments:

    .. cpp:function:: OcaStatus GetNSegments(OcaUint8 &n, OcaUint8 &minN, OcaUint8 &maxN)

        Gets the number of curve segments. The return value indicates whether the value was successfully retrieved.

        This method has id ``4.1``.

        :param OcaUint8 n: Output parameter.
        :param OcaUint8 minN: Output parameter.
        :param OcaUint8 maxN: Output parameter.

    .. _ocadynamicscurve_setnsegments:

    .. cpp:function:: OcaStatus SetNSegments(OcaUint8 Slope)

        Sets the number of curve segments. The return value indicates whether the data was successfully set. If this method increases the value of n, the data in properties  **Threshold** ,  **Slope** , and  **KneeParameter** of the new segment are by default set to the values of the previous segment.

        This method has id ``4.2``.

        :param OcaUint8 Slope: Input parameter.

    .. _ocadynamicscurve_getthreshold:

    .. cpp:function:: OcaStatus GetThreshold(OcaList<OcaDBr> &Threshold, OcaDBz &minThreshold, OcaDBz &maxThreshold)

        Gets the list of Threshold values. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.3``.

        :param OcaList<OcaDBr> Threshold: Output parameter.
        :param OcaDBz minThreshold: Output parameter.
        :param OcaDBz maxThreshold: Output parameter.

    .. _ocadynamicscurve_setthreshold:

    .. cpp:function:: OcaStatus SetThreshold(OcaList<OcaDBr> Threshold)

        Sets the list of Threshold values. The return value indicates whether the values were successfully set.

        This method has id ``4.4``.

        :param OcaList<OcaDBr> Threshold: Input parameter.

    .. _ocadynamicscurve_getslope:

    .. cpp:function:: OcaStatus GetSlope(OcaList<OcaFloat32> &slope, OcaList<OcaFloat32> &minSlope, OcaList<OcaFloat32> &maxSlope)

        Gets the list of Slope values. The return value indicates whether the list was successfully retrieved.

        This method has id ``4.5``.

        :param OcaList<OcaFloat32> slope: Output parameter.
        :param OcaList<OcaFloat32> minSlope: Output parameter.
        :param OcaList<OcaFloat32> maxSlope: Output parameter.

    .. _ocadynamicscurve_setslope:

    .. cpp:function:: OcaStatus SetSlope(OcaList<OcaFloat32> slope)

        Sets the list of Slope values. The return value indicates whether the values were successfully set.

        This method has id ``4.6``.

        :param OcaList<OcaFloat32> slope: Input parameter.

    .. _ocadynamicscurve_getkneeparameter:

    .. cpp:function:: OcaStatus GetKneeParameter(OcaList<OcaFloat32> &parameter, OcaList<OcaFloat32> &minParameter, OcaList<OcaFloat32> &maxParameter)

        Gets the list of KneeParameter valuess. The return value indicates whether the list was successfully retrieved.

        This method has id ``4.7``.

        :param OcaList<OcaFloat32> parameter: Output parameter.
        :param OcaList<OcaFloat32> minParameter: Output parameter.
        :param OcaList<OcaFloat32> maxParameter: Output parameter.

    .. _ocadynamicscurve_setkneeparameter:

    .. cpp:function:: OcaStatus SetKneeParameter(OcaList<OcaFloat32> parameter)

        Sets the list of KneeParameter values. The return value indicates whether the values were successfully set.

        This method has id ``4.8``.

        :param OcaList<OcaFloat32> parameter: Input parameter.

    .. _ocadynamicscurve_getdynamicgainceiling:

    .. cpp:function:: OcaStatus GetDynamicGainCeiling(OcaDB &gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the value of the DynamicGainCeiling property. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.9``.

        :param OcaDB gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. _ocadynamicscurve_setdynamicgainceiling:

    .. cpp:function:: OcaStatus SetDynamicGainCeiling(OcaDB gain)

        Sets the value of the DynamicGainCeiling property. The return value indicates whether the data was successfully set.

        This method has id ``4.10``.

        :param OcaDB gain: Input parameter.

    .. _ocadynamicscurve_getdynamicgainfloor:

    .. cpp:function:: OcaStatus GetDynamicGainFloor(OcaDB &Gain, OcaDB &minGain, OcaDB &maxGain)

        Gets the value of the DynamicGainFloor property. The return value indicates whether the data was successfully retrieved.

        This method has id ``4.11``.

        :param OcaDB Gain: Output parameter.
        :param OcaDB minGain: Output parameter.
        :param OcaDB maxGain: Output parameter.

    .. _ocadynamicscurve_setdynamicgainfloor:

    .. cpp:function:: OcaStatus SetDynamicGainFloor(OcaDB Gain)

        Sets the value of the DynamicGainFloor property. The return value indicates whether the data was successfully set.

        This method has id ``4.12``.

        :param OcaDB Gain: Input parameter.

    .. _ocadynamicscurve_setmultiple:

    .. cpp:function:: OcaStatus SetMultiple(OcaParameterMask Mask, OcaUint8 nSegments, OcaList<OcaDBr> Threshold[], OcaList<OcaFloat32> Slope[], OcaList<OcaFloat32> KneeParameter[], OcaDB DynamicGainFloor, OcaDB DynamicGainCeiling)

        Sets some or all dynamics curve parameters. The return value indicates if the parameters were successfully set. The action of this method is atomic - if any of the value changes fails, none of the changes are made.

        This method has id ``4.13``.

        :param OcaParameterMask Mask: Input parameter.
        :param OcaUint8 nSegments: Input parameter.
        :param OcaList<OcaDBr> Threshold[]: Input parameter.
        :param OcaList<OcaFloat32> Slope[]: Input parameter.
        :param OcaList<OcaFloat32> KneeParameter[]: Input parameter.
        :param OcaDB DynamicGainFloor: Input parameter.
        :param OcaDB DynamicGainCeiling: Input parameter.


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
    
    


