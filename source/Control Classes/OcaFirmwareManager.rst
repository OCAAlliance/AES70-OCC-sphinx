.. _ocafirmwaremanager:

1.3.3  OcaFirmwareManager
=========================

Extends :ref:`OcaManager <ocamanager>`.

.. cpp:class:: OcaFirmwareManager: OcaManager

    Optional manager that manages versions of the different firmware and
    software images of the device.
    
    - May be instantiated at most once in any device.
    
    
    - If instantiated, must have object number 3.
    A device that does not support firmware updating may support the
    subset of this class's functions needed to report firmware version
    numbers to inquiring controllers. This firmware manager offers a
    generic interface for updating OCA devices. The actual robustness of
    the update process is left up to the implementer. The interface allows
    for any of: - Fully transactional based uploads (i.e. only committing
    to the newly uploaded images after all component uploads have
    succeeded, and reverting back to the old images if any step fails) -
    Partly transactional based uploads (i.e. committing to a newly
    uploaded image after each individual component upload succeeds,
    possibly leading to a device containing a mix of old and new images) -
    Non-transactional based uploads guarded by golden images (i.e.
    accepting a 'weak' spot in the upload process where interruption may
    lead to a corrupt regular image, which is solved by loading a
    read-only failsafe ("golden") image in such cases that will allow
    recovery of the regular image) - Non-transactional based uploads that
    may lead to bricked devices

    .. cpp:member:: OcaClassID ClassID

        This property has id ``3.0``.

        Number that uniquely identifies the class. Note that this differs from
        the object number, which identifies the instantiated object. This
        property is an override of the **OcaRoot** property.

    .. cpp:member:: OcaClassVersionNumber ClassVersion

        This property has id ``3.0``.

        Identifies the interface version of the class. Any change to the class
        definition leads to a higher class version. This property is an
        override of the **OcaRoot** property.

    .. cpp:member:: OcaList<OcaVersion> ComponentVersions

        This property has id ``3.0``.

        List of the versions of the components of the device. As of version 2
        of this class, component numbers are of datatype **OcaEnum,** rather
        than the previous **OcaUint16.**

    .. cpp:function:: OcaStatus GetComponentVersions(OcaList<OcaVersion> &componentVersions)

        This method has id ``3.1``.

        Gets the value of the ComponentVersions property. The return value
        indicates whether the property was successfully retrieved.

        :param OcaList<OcaVersion> componentVersions: Output parameter.

    .. cpp:function:: OcaStatus StartUpdateProcess()

        This method has id ``3.2``.

        Marks the start of the update process of an OCA device, meaning one or
        more components will be updated. If the method succeeds the device
        will be in state 'Updating'. One or more active or passive updates can
        then follow, after which the update process is ended by calling the
        '03m08 EndUpdateProcess' method. The return value indicates if
        starting the update process succeeded.


    .. cpp:function:: OcaStatus BeginActiveImageUpdate(OcaComponent component)

        This method has id ``3.3``.

        Starts an active update of a software/firmware image on the device.
        This generic interface can be used to update any component which can
        be updated actively, i.e. where the upload tool actively pushes the
        software/firmware image to the firmware manager. The actual firmware
        manager implementation may implement separate processes for different
        components, but in each case the interface is the same. The active
        interface consists of this method and the methods 03m03 AddImageData,
        03m04 VerifyImage and 03m05 EndActiveImageUpdate. The return value
        indicates if starting the active update succeeded.

        :param OcaComponent component: Input parameter.

    .. cpp:function:: OcaStatus AddImageData(OcaUint32 id, OcaBlob imageData)

        This method has id ``3.4``.

        Adds a new part of the software/firmware image to the upgrade memory
        as part of the active update. Where this data is stored, is up to the
        implementation of the manager. It can either be stored in RAM to be
        written to Flash later, or directly to Flash, dependent on the chosen
        architecture and requirements. The return value indicates whether the
        data is correctly received and the data is not out of order.

        :param OcaUint32 id: Input parameter.
        :param OcaBlob imageData: Input parameter.

    .. cpp:function:: OcaStatus VerifyImage(OcaBlob verifyData)

        This method has id ``3.5``.

        Verifies the entire host processor image using the passed verification
        data.

        :param OcaBlob verifyData: Input parameter.

    .. cpp:function:: OcaStatus EndActiveImageUpdate()

        This method has id ``3.6``.

        Ends the active software/firmware image update. This is needed to let
        the device know that the current active component has finished, and
        therefore a new active or passive update can be started (or the upload
        process can be ended by invoking the '03m08 EndUpdateProcess' method).
        The return value indicates if ending the active update succeeded.


    .. cpp:function:: OcaStatus BeginPassiveComponentUpdate(OcaComponent component, OcaNetworkAddress serverAddress, OcaString updateFileName)

        This method has id ``3.7``.

        Begin a passive software/firmware component update. This generic
        interface can be used for any component that can be passively updated,
        i.e. where the device requests the actual software/firmware image from
        an external server. In the function the component type, details of the
        server and the filename of the file containing the component
        software/firmware image needs to be passed. The device will try to
        retrieve the new software/firmware image from the server and update
        its component using this image. The actual method for retrieving the
        image (e.g. TFTP) and the underlying update technique (e.g. netflash)
        depend on the implementation and may differ between components. Just
        the interface is standardized.

        :param OcaComponent component: Input parameter.
        :param OcaNetworkAddress serverAddress: Input parameter.
        :param OcaString updateFileName: Input parameter.

    .. cpp:function:: OcaStatus EndUpdateProcess()

        This method has id ``3.8``.

        Ends the current update process in which one or more components haven
        been updated (actively or passively). This action will trigger the
        device to start using the new images. This should bring the device
        back into standard operational mode (e.g. rebooting the device, this
        however depends on the implementation of the upgrade process). As it
        will usually trigger a reset of the device in some cases no response
        parameter is used for this method.


