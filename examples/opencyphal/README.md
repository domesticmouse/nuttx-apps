# opencyphal

## Overview
OpenCyphal Cyphal/CAN example (`opencyphal`). Enable the LIBOPENCYPHAL example

## Interface
- `[Kconfig:EXAMPLES_LIBOPENCYPHAL]` - Build configuration option `EXAMPLES_LIBOPENCYPHAL`
- `[Kconfig:EXAMPLES_LIBOPENCYPHAL_DEV]` - Build configuration option `EXAMPLES_LIBOPENCYPHAL_DEV`
- `[Makefile:PROGNAME]` - Registers application/module target `opencyphal`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `opencyphal`
- `[socketcan.h:struct canardsocketinstance]` - Structure definition `canardsocketinstance`
- `[socketcan.h:socketcanopen]` - Public function declaration `socketcanopen()`
- `[socketcan.h:socketcantransmit]` - Public function declaration `socketcantransmit()`
- `[socketcan.h:socketcanreceive]` - Public function declaration `socketcanreceive()`
- `[socketcan.h:socketcanconfigurefilter]` - Public function declaration `socketcanconfigurefilter()`
- `[canard_main.c:getmonotonictimestampusec]` - Public function `getmonotonictimestampusec()`
- `[canard_main.c:process1hztasks]` - Public function `process1hztasks()`
- `[canard_main.c:processtxrxonce]` - Public function `processtxrxonce()`
- `[canard_main.c:opencyphal_main]` - Application entry point `opencyphal_main()`
- `[socketcan.c:socketcanopen]` - Public function `socketcanopen()`
- `[socketcan.c:socketcantransmit]` - Public function `socketcantransmit()`
- `[socketcan.c:socketcanreceive]` - Public function `socketcanreceive()`
- `[socketcan.c:socketcanconfigurefilter]` - Public function `socketcanconfigurefilter()`

## Invariants
- `[Kconfig:depends on CANUTILS_LIBOPENCYPHAL]` - Requires kernel/app configuration `CANUTILS_LIBOPENCYPHAL`
- `[canard_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[canard_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[canard_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[socketcan.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[socketcan.c:bind]` - Binds socket descriptors to local addresses via `bind()`

## Verification
- Run: `make test`
