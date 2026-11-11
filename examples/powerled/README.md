# powerled

## Overview
Powerled example (`powerled`). Enable the powerled driver example

## Interface
- `[Kconfig:EXAMPLES_POWERLED]` - Build configuration option `EXAMPLES_POWERLED`
- `[Kconfig:EXAMPLES_POWERLED_DEVPATH]` - Build configuration option `EXAMPLES_POWERLED_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `powerled`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `powerled`
- `[powerled_main.c:struct args_s]` - Structure definition `args_s`
- `[powerled_main.c:enum powerled_main_mode_e]` - Enumeration `powerled_main_mode_e`
- `[powerled_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DRIVERS_POWERLED]` - Requires kernel/app configuration `DRIVERS_POWERLED`
- `[Kconfig:depends on LIBC_FLOATINGPOINT]` - Requires kernel/app configuration `LIBC_FLOATINGPOINT`
- `[powerled_main.c:CONFIG_NSH_ARCHINIT]` - Configuration guard on `CONFIG_NSH_ARCHINIT`
- `[powerled_main.c:CONFIG_BOARDCTL_FINALINIT]` - Configuration guard on `CONFIG_BOARDCTL_FINALINIT`

## Side Effects
- `[powerled_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[powerled_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[powerled_main.c:open]` - Opens device nodes or files via `open()`
- `[powerled_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
