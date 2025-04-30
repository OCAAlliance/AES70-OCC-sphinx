*******************
Operating Datatypes
*******************

.. _OcaSecurityType:

OcaSecurityType
===============

.. cpp:enum:: OcaSecurityType : uint8_t

    Security types for stream endpoints

    .. cpp:enumerator:: None = 0

        No security

    .. cpp:enumerator:: Default = 1

        Default security type for the current context

.. _OcaLockState:

OcaLockState
============

.. cpp:enum:: OcaLockState : uint8_t

    Lock state of object

    .. cpp:enumerator:: NoLock = 0

        Not locked

    .. cpp:enumerator:: LockNoWrite = 1

        Others may read but not write. Lockholder may write.

    .. cpp:enumerator:: LockNoReadWrite = 2

        No one except lockholder may read or write.

.. _OcaStatus:

OcaStatus
=========

.. cpp:enum:: OcaStatus : uint8_t

    Standard status codes returned from method calls.

    .. cpp:enumerator:: OK = 0

        Method call was successful.

    .. cpp:enumerator:: ProtocolVersionError = 1

        Controller sent a Control Protocol PDU whose protocol version the Device
        cannot handle.

    .. cpp:enumerator:: DeviceError = 2

        Command execution failed due to an internal Device error.

    .. cpp:enumerator:: Locked = 3

        Command attempted to access an object with a lock status too restrictive
        for the requested operation.

    .. cpp:enumerator:: BadFormat = 4

        One or more method parameters in a Command was in an invalid format.

    .. cpp:enumerator:: BadONo = 5

        Object number in a Command referenced a nonexistent object.

    .. cpp:enumerator:: ParameterError = 6

        One or more method parameters given in a Command was unacceptable in the
        current context, or a required parameter was missing.

    .. cpp:enumerator:: ParameterOutOfRange = 7

        One or more parameter values given in a Command was too large or too
        small for the current context.

    .. cpp:enumerator:: NotImplemented = 8

        Method ID in Command referenced a method the Device does not implement.

    .. cpp:enumerator:: InvalidRequest = 9

        Command requested an action that is invalid in the current context.

    .. cpp:enumerator:: ProcessingFailed = 10

        Command execution failed, but not due to an internal Device error.

    .. cpp:enumerator:: BadMethod = 11

        Method ID in a Command referenced a nonexistent method.

    .. cpp:enumerator:: PartiallySucceeded = 12

        Command execution partly succeeded. Example: in a method that operates
        on a specified list of items, some items were processed successfully,
        some not.

    .. cpp:enumerator:: Timeout = 13

        Device failed to process a Command within the given timeout time. Valid
        only for methods with timeout parameters.

    .. cpp:enumerator:: BufferOverflow = 14

        Device did not have enough available memory to store an incoming PDU.

    .. cpp:enumerator:: PermissionDenied = 15

        Command requested an action for which the Controller had insufficient
        permission.

    .. cpp:enumerator:: OutOfMemory = 16

        Device did not have enough available memory to process the Command.

    .. cpp:enumerator:: Busy = 17

        Command could not be executed because required resources are busy.

