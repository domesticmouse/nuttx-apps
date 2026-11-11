# settings

## Overview
Settings example (`settings`). Enable the "settings" example. This uses the functions provided in system/settings to test the storage and retrieval of various configurable parameters

## Interface
- `[Kconfig:EXAMPLES_SETTINGS]` - Build configuration option `EXAMPLES_SETTINGS`
- `[Kconfig:EXAMPLES_SETTINGS_PROGNAME]` - Build configuration option `EXAMPLES_SETTINGS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SETTINGS_PROGNAME)`
- `[settings_main.c:settings_main]` - Application entry point `settings_main()`

## Invariants
- `[settings_main.c:#error]` - Compile-time precondition: TMPFS must be enabled
- `[settings_main.c:#error]` - Compile-time precondition: LIBC_TMPDIR must be defined
- `[settings_main.c:CONFIG_EXAMPLES_SETTINGS_USE_TMPFS]` - Configuration guard on `CONFIG_EXAMPLES_SETTINGS_USE_TMPFS`
- `[settings_main.c:CONFIG_FS_TMPFS]` - Configuration guard on `CONFIG_FS_TMPFS`
- `[settings_main.c:CONFIG_LIBC_TMPDIR]` - Configuration guard on `CONFIG_LIBC_TMPDIR`

## Side Effects
- `[settings_main.c:open]` - Opens device nodes or files via `open()`
- `[settings_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
