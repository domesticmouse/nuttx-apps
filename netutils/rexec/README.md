# `netutils/rexec`

## Overview
Provides Remote execution client (`netutils/rexec`). Enable support for the remote execution client. Warning: rexec transmits passwords in cleartext, unencrypted.

## Interface
- [Makefile:PROGNAME=rexec]
- [Kconfig:CONFIG_NETUTILS_REXEC]
- [Kconfig:CONFIG_NETUTILS_REXEC_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_REXEC_STACKSIZE]
- [rexec.c:struct rexec_arg_s]
- [rexec.c:main]

## Invariants
- [Kconfig:CONFIG_NETUTILS_REXEC]: Build and feature compilation gated by `CONFIG_NETUTILS_REXEC`.
- [Kconfig:CONFIG_NETUTILS_REXEC_PRIORITY]: Build and feature compilation gated by `CONFIG_NETUTILS_REXEC_PRIORITY`.

## Side Effects
- [rexec.c:read]: Performs VFS file or device descriptor I/O operations.
- [rexec.c:free]: Allocates or releases dynamic heap memory.
- [rexec.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
