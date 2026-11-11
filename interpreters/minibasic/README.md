# `interpreters/minibasic`

## Overview
Provides Mini Basic Interpreter support (`interpreters/minibasic`). This is a Basic interpreter written by Malcolm McLean

## Interface
- [Makefile:PROGNAME=basic]
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC]
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC_PRIORITY]
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC_STACKSIZE]
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC_IOBUFSIZE]
- [basic.c:struct mb_line_s]
- [basic.c:struct mb_variable_s]
- [basic.c:struct mb_dimvar_s]
- [basic.c:struct mb_lvalue_s]
- [basic.c:struct mb_forloop_s]
- [basic.c:basic]
- [script.c:main]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC]: Build and feature compilation gated by `CONFIG_INTERPRETERS_MINIBASIC`.
- [Kconfig:CONFIG_INTERPRETERS_MINIBASIC_PRIORITY]: Build and feature compilation gated by `CONFIG_INTERPRETERS_MINIBASIC_PRIORITY`.
- [basic.c:assert]: Enforces `assert(0)` precondition.
- [basic.c:assert]: Enforces `assert(ndims <= 5)` precondition.
- [basic.c:assert]: Enforces `assert(end != str)` precondition.
- [basic.c:assert]: Enforces `assert(isalpha(*str))` precondition.

## Side Effects
- [basic.c:malloc]: Allocates or releases dynamic heap memory.
- [basic.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [script.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [script.c:malloc]: Allocates or releases dynamic heap memory.
- [script.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
