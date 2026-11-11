# smps

## Overview
Smps example (`smps`). The default path to the Smps device. Default: /dev/smps0

## Interface
- `[Kconfig:EXAMPLES_SMPS]` - Build configuration option `EXAMPLES_SMPS`
- `[Kconfig:EXAMPLES_SMPS_DEVPATH]` - Build configuration option `EXAMPLES_SMPS_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `smps`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `smps`
- `[smps_main.c:struct args_s]` - Structure definition `args_s`
- `[smps_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DRIVERS_SMPS]` - Requires kernel/app configuration `DRIVERS_SMPS`
- `[Kconfig:depends on LIBC_FLOATINGPOINT]` - Requires kernel/app configuration `LIBC_FLOATINGPOINT`
- `[smps_main.c:CONFIG_EXAMPLES_SMPS_TIME_DEFAULT]` - Configuration guard on `CONFIG_EXAMPLES_SMPS_TIME_DEFAULT`
- `[smps_main.c:CONFIG_EXAMPLES_SMPS_OUT_VOLTAGE_DEFAULT]` - Configuration guard on `CONFIG_EXAMPLES_SMPS_OUT_VOLTAGE_DEFAULT`
- `[smps_main.c:CONFIG_EXAMPLES_SMPS_OUT_CURRENT_DEFAULT]` - Configuration guard on `CONFIG_EXAMPLES_SMPS_OUT_CURRENT_DEFAULT`
- `[smps_main.c:CONFIG_EXAMPLES_SMPS_OUT_POWER_DEFAULT]` - Configuration guard on `CONFIG_EXAMPLES_SMPS_OUT_POWER_DEFAULT`

## Side Effects
- `[smps_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[smps_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[smps_main.c:open]` - Opens device nodes or files via `open()`
- `[smps_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
