# random

## Overview
/dev/random test (`random`). Enable a simple test of /dev/random

## Interface
- `[Kconfig:EXAMPLES_RANDOM]` - Build configuration option `EXAMPLES_RANDOM`
- `[Kconfig:EXAMPLES_MAXSAMPLES]` - Build configuration option `EXAMPLES_MAXSAMPLES`
- `[Makefile:PROGNAME]` - Registers application/module target `rand`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `rand`
- `[random_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DEV_RANDOM]` - Requires kernel/app configuration `DEV_RANDOM`
- `[random_main.c:CONFIG_EXAMPLES_MAXSAMPLES]` - Configuration guard on `CONFIG_EXAMPLES_MAXSAMPLES`
- `[random_main.c:CONFIG_EXAMPLES_NSAMPLES]` - Configuration guard on `CONFIG_EXAMPLES_NSAMPLES`
- `[random_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[random_main.c:/dev/random]` - Opens or interacts with VFS/device path `/dev/random`
- `[random_main.c:open]` - Opens device nodes or files via `open()`
- `[random_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[random_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
