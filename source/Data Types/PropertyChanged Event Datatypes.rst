*******************************
PropertyChanged Event Datatypes
*******************************

.. _OcaPropertyChangeType:

OcaPropertyChangeType
=====================

.. cpp:enum:: OcaPropertyChangeType : uint8_t

    Enum describing property change type.

    .. cpp:enumerator:: CurrentChanged = 1

        Current value has changed.

    .. cpp:enumerator:: MinChanged = 2

        Minimum value has changed. Note that datatypes of min and max may not be
        the same as the datatype of the current value.

    .. cpp:enumerator:: MaxChanged = 3

        Maximum value has changed. Note that datatypes of min and max may not be
        the same as the datatype of the current value.

    .. cpp:enumerator:: ItemAdded = 4

        One or more items of a list, map, or multimap property have been added.
        **PropertyValue** field of event data contains the entire property
        value.

    .. cpp:enumerator:: ItemChanged = 5

        One or more items of a list, map, or multimap property have been
        changed. **PropertyValue** field of event data contains the entire
        property value.

    .. cpp:enumerator:: ItemDeleted = 6

        One or more items of a list, map, or multimap property have been
        deleted. **PropertyValue** field of event data contains the entire
        property value.

.. _OcaPropertyChangedEventData:

OcaPropertyChangedEventData
===========================

.. cpp:struct:: OcaPropertyChangedEventData

    Template class that defines the event data parameter for events that return
    property values, such as the **PropertyChanged** event defined in
    **OcaRoot**, and the **PeriodicObservation** event define in
    **OcaNumericObserver.** The template parameter is the datatype of the
    affected property.

    .. cpp:member:: OcaPropertyID PropertyID

        The property ID of the property that has changed.

    .. cpp:member:: variant PropertyValue

        The new, changed, or deleted data. - "Affected property" means a
        property whose addition, change, or deletion has raised this event. -
        "Affected item" means an added, changed, or deleted member of an
        affected collection property. - "DT" is the template parameter
        **DT:datatype.** The **datatype** of this property shall be **DT,**
        except when the value of **ChangeType** is **ItemAdded2**,
        **ItemChanged2**, or **ItemDeleted2** and the affected property is an
        **OcaList**, in which case the variant type shall be
        **OcaMap<OcaUint16,DT>,** and the value(s) of the map key(s) shall be
        the list index value(s) of the affected item(s). The **value** of this
        property shall be the entire value of the affected property, except when
        the value of **ChangeType** is **ItemAdded2**, **ItemChanged2**, or
        **ItemDeleted2,** in which case the value shall consist of only the
        affected item(s).

    .. cpp:member:: OcaPropertyChangeType ChangeType

        Type of change : Current value, Min, Max, Item changed, Item added, Item
        deleted

