# update_agent_local

## Overview
MCUBoot Local Update Agent (`mcuboot/update_agent_local`). Enable the MCUBoot Local Update Agent example. This application reads a firmware binary from local storage and copies it to the MCUBoot secondary flash slot for update.

## Interface
- `[Kconfig:EXAMPLES_MCUBOOT_LOCAL_AGENT]` - Build configuration option `EXAMPLES_MCUBOOT_LOCAL_AGENT`
- `[Kconfig:EXAMPLES_MCUBOOT_LOCAL_AGENT_PROGNAME]` - Build configuration option `EXAMPLES_MCUBOOT_LOCAL_AGENT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MCUBOOT_LOCAL_AGENT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MCUBOOT_LOCAL_AGENT_PROGNAME}`
- `[mcuboot_local_agent_main.c:struct update_context_s]` - Structure definition `update_context_s`
- `[mcuboot_local_agent_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on BOOT_MCUBOOT]` - Requires kernel/app configuration `BOOT_MCUBOOT`
- `[mcuboot_local_agent_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[mcuboot_local_agent_main.c:/mnt/sdcard/firmware.bin]` - Opens or interacts with VFS/device path `/mnt/sdcard/firmware.bin`
- `[mcuboot_local_agent_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[mcuboot_local_agent_main.c:open]` - Opens device nodes or files via `open()`
- `[mcuboot_local_agent_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mcuboot_local_agent_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
