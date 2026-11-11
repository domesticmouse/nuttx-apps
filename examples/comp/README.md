# comp

## Overview
Comparator tool (`comp`). Enable support for the comparator tool.

## Interface
- `[Kconfig:EXAMPLES_COMP]` - Build configuration option `EXAMPLES_COMP`
- `[Kconfig:EXAMPLES_COMP_PROGNAME]` - Build configuration option `EXAMPLES_COMP_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_COMP_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_COMP_PROGNAME}`
- `[comp_main.c:struct comp_state_s]` - Structure definition `comp_state_s`
- `[comp_main.c:main]` - Application entry point `main()`
- `[comp_main.c:getopt]` - Command-line option parser supporting flags `"p:D:s:f:i:w:edrth"`
- `[comp_main.c:getopt]` - Command-line option parser supporting flags `"p:edrth"`

## Invariants
- `[Kconfig:depends on COMP]` - Requires kernel/app configuration `COMP`
- `[Kconfig:depends on DAC]` - Requires kernel/app configuration `DAC`
- `[comp_main.c:#error]` - Compile-time precondition: COMP device support is not enabled (CONFIG_COMP)
- `[comp_main.c:CONFIG_DAC]` - Configuration guard on `CONFIG_DAC`
- `[comp_main.c:CONFIG_COMP]` - Configuration guard on `CONFIG_COMP`
- `[comp_main.c:CONFIG_EXAMPLES_COMP_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_COMP_DEVPATH`
- `[comp_main.c:CONFIG_EXAMPLES_COMP_DACPATH]` - Configuration guard on `CONFIG_EXAMPLES_COMP_DACPATH`
- `[comp_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[comp_main.c:/dev/comp0]` - Opens or interacts with VFS/device path `/dev/comp0`
- `[comp_main.c:/dev/dac0]` - Opens or interacts with VFS/device path `/dev/dac0`
- `[comp_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[comp_main.c:open]` - Opens device nodes or files via `open()`
- `[comp_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[comp_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[comp_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
