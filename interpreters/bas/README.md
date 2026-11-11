# `interpreters/bas`

## Overview
Provides Basic Interpreter support (`interpreters/bas`). This is a Basic interpreter written by Michael Haardt

## Interface
- [Makefile:PROGNAME=bas]
- [Kconfig:CONFIG_INTERPRETERS_BAS]
- [Kconfig:CONFIG_INTERPRETERS_BAS_VERSION]
- [Kconfig:CONFIG_INTERPRETERS_BAS_PRIORITY]
- [Kconfig:CONFIG_INTERPRETERS_BAS_STACKSIZE]
- [bas.h:bas_init]
- [bas.h:bas_runFile]
- [bas.h:bas_runLine]
- [bas.h:bas_interpreter]
- [bas.h:bas_exit]
- [bas.h:STDCHANNEL]
- [bas.h:LPCHANNEL]
- [bas_auto.h:struct Auto]
- [bas_auto.h:struct AutoFrameSlot]
- [bas_auto.h:struct AutoExceptionSlot]
- [bas_auto.h:union AutoSlot]
- [bas_auto.h:Auto_new]
- [bas_auto.h:Auto_destroy]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_BAS]: Build and feature compilation gated by `CONFIG_INTERPRETERS_BAS`.
- [Kconfig:CONFIG_INTERPRETERS_BAS_VERSION]: Build and feature compilation gated by `CONFIG_INTERPRETERS_BAS_VERSION`.
- [Kconfig:depends on ARCH_HAVE_FORK && EXPERIMENTAL]: Requires Kconfig dependency condition `ARCH_HAVE_FORK && EXPERIMENTAL`.
- [Kconfig:depends on EXAMPLES_BAS_SHELL]: Requires Kconfig dependency condition `EXAMPLES_BAS_SHELL`.
- [bas_value.h:assert]: Enforces `assert((this)!=(struct Value*)0)` precondition.
- [bas_value.h:assert]: Enforces `assert(0)` precondition.

## Side Effects
- [bas_value.h:free]: Allocates or releases dynamic heap memory.
- [bas.c:open]: Performs VFS file or device descriptor I/O operations.
- [bas.c:realloc]: Allocates or releases dynamic heap memory.
- [bas_auto.c:free]: Allocates or releases dynamic heap memory.
- [bas_fs.c:read]: Performs VFS file or device descriptor I/O operations.
- [bas_fs.c:realloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
