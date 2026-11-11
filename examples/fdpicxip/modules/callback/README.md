# callback

## Overview
NuttX `fdpicxip/modules/callback` component: Hands a module function to the firmware every way the firmware will accept one. In FDPIC a function pointer is the address of a two-word descriptor, not a code address, and that descriptor lives in the module's writable segment in RAM.  Firmware that stores such a pointer and later branches to it th

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `callback`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `callback`
- `[callback.c:main]` - Application entry point `main()`

## Invariants
- `[callback.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[callback.c:/mnt/xipfs]` - Opens or interacts with VFS/device path `/mnt/xipfs`
- `[callback.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[callback.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[callback.c:timer_create]` - Creates POSIX interval timers via `timer_create()`
- `[callback.c:sigaction]` - Registers signal handlers via `sigaction()`
- `[callback.c:mq_open]` - Opens POSIX message queues via `mq_open()`
- `[callback.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
