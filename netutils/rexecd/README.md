# `netutils/rexecd`

## Overview
Provides Remote Execution Server (`netutils/rexecd`). Enable support for the Remote Execution server. Warning: rexec transmits passwords in cleartext, unencrypted.

## Interface
- [Makefile:PROGNAME=rexecd]
- [Kconfig:CONFIG_NETUTILS_REXECD]
- [Kconfig:CONFIG_NETUTILS_REXECD_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_REXECD_STACKSIZE]
- [rexecd.c:main]

## Invariants
- [Kconfig:CONFIG_NETUTILS_REXECD]: Build and feature compilation gated by `CONFIG_NETUTILS_REXECD`.
- [Kconfig:CONFIG_NETUTILS_REXECD_PRIORITY]: Build and feature compilation gated by `CONFIG_NETUTILS_REXECD_PRIORITY`.

## Side Effects
- [rexecd.c:read]: Performs VFS file or device descriptor I/O operations.
- [rexecd.c:send]: Performs network socket creation, binding, or protocol I/O.
- [rexecd.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [rexecd.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
