.. _ocadelayextended:

1.1.1.7.1  OcaDelayExtended
===========================

Class Hierarchy:

:ref:`OcaRoot <ocaroot>` : :ref:`OcaWorker <ocaworker>` : :ref:`OcaActuator <ocaactuator>` : :ref:`OcaDelay <ocadelay>` : :ref:`OcaDelayExtended <ocadelayextended>`

.. cpp:class:: OcaDelayExtended: OcaDelay

    Signal delay - extended version. Allows setting delay value in various
    units. Note that the inherited property 04p01 DelayTime is also supported by
    this class and reflects actual achieved delay in seconds.

    **Properties**:


    .. _ocadelayextended_classid:

    .. cpp:member:: static const OcaClassID ClassID = "1.1.1.7.1"

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

        This property has id ``1.1``.

    .. _ocadelayextended_classversion:

    .. cpp:member:: static const OcaClassVersionNumber ClassVersion = 2

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an override
        of the **OcaRoot** property.

        This property has id ``1.2``.

    .. _ocadelayextended_delayvalue:

    .. cpp:member:: OcaDelayValue DelayValue

        Delay value.

        This property has id ``5.1``.

    Properties inherited from :ref:`ocadelay`:

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

    - :cpp:texpr:`OcaClassID` :ref:`OcaDelay::ClassID <ocadelay_classid>`

    - :cpp:texpr:`OcaClassVersionNumber` :ref:`OcaDelay::ClassVersion <ocadelay_classversion>`

    - :cpp:texpr:`OcaTimeInterval` :ref:`OcaDelay::DelayTime <ocadelay_delaytime>`


    **Methods**:


    .. _ocadelayextended_getdelayvalue:

    .. cpp:function:: OcaStatus GetDelayValue(OcaDelayValue &Value, OcaDelayValue &minValue, OcaDelayValue &maxValue)

        Gets the value of the DelayValue property. The return value indicates
        whether the property was successfully retrieved.

        This method has id ``5.1``.

        - :cpp:expr:`Value`: Output parameter.


        - :cpp:expr:`minValue`: Output parameter.


        - :cpp:expr:`maxValue`: Output parameter.


    .. _ocadelayextended_setdelayvalue:

    .. cpp:function:: OcaStatus SetDelayValue(OcaDelayValue Value)

        Sets the value of the DelayValue property. The return value indicates
        whether the property was successfully set.

        This method has id ``5.2``.

        - :cpp:expr:`Value`: Input parameter.


    .. _ocadelayextended_getdelayvalueconverted:

    .. cpp:function:: OcaStatus GetDelayValueConverted(OcaDelayUnit UoM, OcaDelayValue &Value)

        Return current delay setting, converted to given units. The return value
        indicates whether the method has succeeded.

        This method has id ``5.3``.

        - :cpp:expr:`UoM`: Input parameter.


        - :cpp:expr:`Value`: Output parameter.


    Methods inherited from :ref:`ocadelay`:

    - :ref:`OcaDelay::GetClassIdentification <ocaroot_getclassidentification>`

    - :ref:`OcaDelay::GetLockable <ocaroot_getlockable>`

    - :ref:`OcaDelay::LockTotal <ocaroot_locktotal>`

    - :ref:`OcaDelay::Unlock <ocaroot_unlock>`

    - :ref:`OcaDelay::GetRole <ocaroot_getrole>`

    - :ref:`OcaDelay::LockReadonly <ocaroot_lockreadonly>`

    - :ref:`OcaDelay::GetEnabled <ocaworker_getenabled>`

    - :ref:`OcaDelay::SetEnabled <ocaworker_setenabled>`

    - :ref:`OcaDelay::AddPort <ocaworker_addport>`

    - :ref:`OcaDelay::DeletePort <ocaworker_deleteport>`

    - :ref:`OcaDelay::GetPorts <ocaworker_getports>`

    - :ref:`OcaDelay::GetPortName <ocaworker_getportname>`

    - :ref:`OcaDelay::SetPortName <ocaworker_setportname>`

    - :ref:`OcaDelay::GetLabel <ocaworker_getlabel>`

    - :ref:`OcaDelay::SetLabel <ocaworker_setlabel>`

    - :ref:`OcaDelay::GetOwner <ocaworker_getowner>`

    - :ref:`OcaDelay::GetLatency <ocaworker_getlatency>`

    - :ref:`OcaDelay::SetLatency <ocaworker_setlatency>`

    - :ref:`OcaDelay::GetPath <ocaworker_getpath>`

    - :ref:`OcaDelay::GetDelayTime <ocadelay_getdelaytime>`

    - :ref:`OcaDelay::SetDelayTime <ocadelay_setdelaytime>`

