# posix_stdio

## Overview
Posix stdio example (`posix_stdio`). Enable POSIX stdio example that shows how to use open(), write() and close() via /dev/console.

## Interface
- `[Kconfig:EXAMPLES_POSIX_STDIO]` - Build configuration option `EXAMPLES_POSIX_STDIO`
- `[Kconfig:EXAMPLES_POSIX_STDIO_PROGNAME]` - Build configuration option `EXAMPLES_POSIX_STDIO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_POSIX_STDIO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_POSIX_STDIO_PROGNAME}`
- `[posix_stdio.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on EXAMPLES_POSIX_STDIO]` - Requires kernel/app configuration `EXAMPLES_POSIX_STDIO`
- `[Kconfig:depends on EXAMPLES_POSIX_STDIO]` - Requires kernel/app configuration `EXAMPLES_POSIX_STDIO`
- `[Kconfig:depends on EXAMPLES_POSIX_STDIO]` - Requires kernel/app configuration `EXAMPLES_POSIX_STDIO`

## Side Effects
- `[posix_stdio.c:/dev/console]` - Opens or interacts with VFS/device path `/dev/console`
- `[posix_stdio.c:open]` - Opens device nodes or files via `open()`
- `[posix_stdio.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
