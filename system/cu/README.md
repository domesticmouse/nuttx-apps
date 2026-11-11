# `system/cu`

## Overview
Provides CU minimal serial terminal (`system/cu`). Enable the CU serial terminal. This is a minimalistic implementation of the 'cu' terminal program (part of Taylor UUCP for

## Interface
- [Makefile:PROGNAME=cu]
- [Kconfig:CONFIG_SYSTEM_CUTERM]
- [Kconfig:CONFIG_SYSTEM_CUTERM_DEFAULT_DEVICE]
- [Kconfig:CONFIG_SYSTEM_CUTERM_DEFAULT_BAUD]
- [Kconfig:CONFIG_SYSTEM_CUTERM_STACKSIZE]
- [cu_main.c:enum parity_mode]
- [cu_main.c:struct cu_globals_s]
- [cu_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CUTERM]: Build and feature compilation gated by `CONFIG_SYSTEM_CUTERM`.
- [Kconfig:CONFIG_SYSTEM_CUTERM_DEFAULT_DEVICE]: Build and feature compilation gated by `CONFIG_SYSTEM_CUTERM_DEFAULT_DEVICE`.
- [cu_main.c:CONFIG_SYSTEM_CUTERM_DEFAULT_DEVICE]: Conditional compilation gated by `CONFIG_SYSTEM_CUTERM_DEFAULT_DEVICE`.
- [cu_main.c:CONFIG_SYSTEM_CUTERM_DEFAULT_BAUD]: Conditional compilation gated by `CONFIG_SYSTEM_CUTERM_DEFAULT_BAUD`.
- [cu_main.c:CONFIG_SYSTEM_CUTERM_DISABLE_ERROR_PRINT]: Conditional compilation gated by `CONFIG_SYSTEM_CUTERM_DISABLE_ERROR_PRINT`.
- [cu_main.c:CONFIG_ENABLE_ALL_SIGNALS]: Conditional compilation gated by `CONFIG_ENABLE_ALL_SIGNALS`.

## Side Effects
- [cu_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [cu_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [cu_main.c:dprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
