# dronecan

## Overview
DroneCAN example (`dronecan`). Enable the LIBDRONECAN example

## Interface
- `[Kconfig:EXAMPLES_DRONECAN]` - Build configuration option `EXAMPLES_DRONECAN`
- `[Kconfig:EXAMPLES_DRONECAN_DEVPATH]` - Build configuration option `EXAMPLES_DRONECAN_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `dronecan`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `dronecan`
- `[canard_main.c:getMonotonicTimestampUSec]` - Public function `getMonotonicTimestampUSec()`
- `[canard_main.c:makeNodeStatusMessage]` - Public function `makeNodeStatusMessage()`
- `[canard_main.c:process1HzTasks]` - Public function `process1HzTasks()`
- `[canard_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on CANUTILS_LIBDRONECAN]` - Requires kernel/app configuration `CANUTILS_LIBDRONECAN`
- `[Kconfig:depends on CAN]` - Requires kernel/app configuration `CAN`
- `[canard_main.c:CONFIG_NET_CAN_CANFD]` - Configuration guard on `CONFIG_NET_CAN_CANFD`
- `[canard_main.c:CONFIG_NET_CAN]` - Configuration guard on `CONFIG_NET_CAN`
- `[canard_main.c:CONFIG_DEBUG_CAN]` - Configuration guard on `CONFIG_DEBUG_CAN`
- `[canard_main.c:CONFIG_CAN]` - Configuration guard on `CONFIG_CAN`
- `[canard_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[canard_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[canard_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[canard_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
