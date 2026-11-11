# dac

## Overview
DAC tool (`dac`). Enable support for the DAC tool.

## Interface
- `[Kconfig:EXAMPLES_DAC]` - Build configuration option `EXAMPLES_DAC`
- `[Kconfig:EXAMPLES_DAC_DEVPATH]` - Build configuration option `EXAMPLES_DAC_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `dac`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `dac`
- `[dac_main.c:struct command]` - Structure definition `command`
- `[dac_main.c:struct dac_state_s]` - Structure definition `dac_state_s`
- `[dac_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DAC]` - Requires kernel/app configuration `DAC`
- `[dac_main.c:#error]` - Compile-time precondition: DAC device support is not enabled (CONFIG_DAC)
- `[dac_main.c:CONFIG_DAC]` - Configuration guard on `CONFIG_DAC`
- `[dac_main.c:CONFIG_EXAMPLES_DAC_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_DAC_DEVPATH`
- `[dac_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[dac_main.c:/dev/dac0]` - Opens or interacts with VFS/device path `/dev/dac0`
- `[dac_main.c:open]` - Opens device nodes or files via `open()`
- `[dac_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[dac_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
