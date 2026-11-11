# `industry/modbus/freemodbus/nuttx`

## Overview
Implements `industry/modbus/freemodbus/nuttx` source and header components (`port.h`, `portevent.c`, `portevent_m.c`, `portother.c` and 5 more files) in the NuttX application tree.

## Interface
- [port.h:eMBPortLogLevel]
- [port.h:vMBPortEnterCritical]
- [port.h:vMBPortExitCritical]
- [port.h:vMBPortLog]
- [port.h:vMBPortTimerPoll]
- [port.h:xMBPortSerialPoll]
- [port.h:xMBPortSerialSetTimeout]
- [port.h:INLINE]
- [port.h:ENTER_CRITICAL_SECTION]
- [port.h:EXIT_CRITICAL_SECTION]
- [portevent.c:xMBPortEventInit]
- [portevent.c:xMBPortEventPost]
- [portevent.c:xMBPortEventGet]
- [portevent_m.c:xMBMasterPortEventInit]
- [portevent_m.c:xMBMasterPortEventPost]
- [portevent_m.c:xMBMasterPortEventGet]
- [portevent_m.c:vMBMasterOsResInit]
- [portevent_m.c:xMBMasterRunResTake]

## Invariants
- [port.h:CONFIG_INDUSTRY_MODBUS_DISABLE_LOG]: Conditional compilation gated by `CONFIG_INDUSTRY_MODBUS_DISABLE_LOG`.
- [port.h:CONFIG_MB_RTU_MASTER]: Conditional compilation gated by `CONFIG_MB_RTU_MASTER`.
- [port.h:CONFIG_MB_ASCII_MASTER]: Conditional compilation gated by `CONFIG_MB_ASCII_MASTER`.
- [portevent_m.c:sem_wait]: Synchronizes concurrent access across threads or critical sections.
- [portevent_m.c:CONFIG_MB_RTU_MASTER]: Conditional compilation gated by `CONFIG_MB_RTU_MASTER`.
- [portevent_m.c:CONFIG_MB_ASCII_MASTER]: Conditional compilation gated by `CONFIG_MB_ASCII_MASTER`.

## Side Effects
- [portserial.c:read]: Performs VFS file or device descriptor I/O operations.
- [portserial_m.c:read]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
