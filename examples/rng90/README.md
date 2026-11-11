# rng90

## Overview
Microchip RNG90 TRNG example (`rng90`). Enable the RNG90 example.  It opens the RNG90 character device, runs the built-in self-test and reads random bytes from it.

## Interface
- `[Kconfig:EXAMPLES_RNG90]` - Build configuration option `EXAMPLES_RNG90`
- `[Kconfig:EXAMPLES_RNG90_PROGNAME]` - Build configuration option `EXAMPLES_RNG90_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_RNG90_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_RNG90_PROGNAME}`
- `[rng90_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DEV_RNG90]` - Requires kernel/app configuration `DEV_RNG90`
- `[rng90_main.c:CONFIG_EXAMPLES_RNG90_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_RNG90_DEVPATH`
- `[rng90_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[rng90_main.c:/dev/rng0]` - Opens or interacts with VFS/device path `/dev/rng0`
- `[rng90_main.c:open]` - Opens device nodes or files via `open()`
- `[rng90_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[rng90_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
