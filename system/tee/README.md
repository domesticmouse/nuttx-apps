# `system/tee`

## Overview
Provides Tee Command (`system/tee`). Enable support for the tee command.

## Interface
- [Makefile:PROGNAME=tee]
- [Kconfig:CONFIG_SYSTEM_TEE]
- [Kconfig:CONFIG_SYSTEM_TEE_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_TEE_PRIORITY]
- [tee.c:struct tee_list_s]
- [tee.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TEE]: Build and feature compilation gated by `CONFIG_SYSTEM_TEE`.
- [Kconfig:CONFIG_SYSTEM_TEE_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_TEE_STACKSIZE`.

## Side Effects
- [tee.c:open]: Performs VFS file or device descriptor I/O operations.
- [tee.c:malloc]: Allocates or releases dynamic heap memory.
- [tee.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
