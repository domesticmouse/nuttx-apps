# chrono

## Overview
Chronometer example to use with STM32LDiscover (`chrono`). Enable the Chronometer example

## Interface
- `[Kconfig:EXAMPLES_CHRONO]` - Build configuration option `EXAMPLES_CHRONO`
- `[Kconfig:EXAMPLES_CHRONO_PROGNAME]` - Build configuration option `EXAMPLES_CHRONO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_CHRONO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_CHRONO_PROGNAME}`
- `[chrono_main.c:struct slcd_chrono_s]` - Structure definition `slcd_chrono_s`
- `[chrono_main.c:enum chronostate_e]` - Enumeration `chronostate_e`
- `[chrono_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SLCD && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `SLCD && ENABLE_ALL_SIGNALS`
- `[chrono_main.c:CONFIG_ENABLE_ALL_SIGNALS]` - Configuration guard on `CONFIG_ENABLE_ALL_SIGNALS`
- `[chrono_main.c:CONFIG_STDIO_LINEBUFFER]` - Configuration guard on `CONFIG_STDIO_LINEBUFFER`

## Side Effects
- `[chrono_main.c:/dev/buttons]` - Opens or interacts with VFS/device path `/dev/buttons`
- `[chrono_main.c:/dev/slcd0]` - Opens or interacts with VFS/device path `/dev/slcd0`
- `[chrono_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[chrono_main.c:open]` - Opens device nodes or files via `open()`
- `[chrono_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[chrono_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[chrono_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[chrono_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
