# `interpreters/quickjs`

## Overview
Provides QuickJS JavaScript interpreter (`interpreters/quickjs`). It's depend on libatomic, Not all platform support it.

## Interface
- [Makefile:PROGNAME=qjs]
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS]
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS_NONE]
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS_MINI]
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS_FULL]
- [qjsmini.c:struct trace_malloc_data]
- [qjsmini.c:js_load_file]
- [qjsmini.c:js_std_add_helpers]
- [qjsmini.c:js_ext_init]
- [qjsmini.c:js_ext_destroy]
- [qjsmini.c:main]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS]: Build and feature compilation gated by `CONFIG_INTERPRETERS_QUICKJS`.
- [Kconfig:CONFIG_INTERPRETERS_QUICKJS_NONE]: Build and feature compilation gated by `CONFIG_INTERPRETERS_QUICKJS_NONE`.
- [Kconfig:depends on INTERPRETERS_QUICKJS_MINI]: Requires Kconfig dependency condition `INTERPRETERS_QUICKJS_MINI`.
- [qjsmini.c:assert]: Enforces `assert(size != 0)` precondition.
- [qjsmini.c:CONFIG_INTERPRETERS_QUICKJS_EXT_HOOK]: Conditional compilation gated by `CONFIG_INTERPRETERS_QUICKJS_EXT_HOOK`.

## Side Effects
- [qjsmini.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [qjsmini.c:free]: Allocates or releases dynamic heap memory.
- [qjsmini.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
