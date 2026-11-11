# lsm6dsl_reader

## Overview
LSM6DSL reader example (`lsm6dsl_reader`). Enable the LSM6DSL reader example

## Interface
- `[Kconfig:EXAMPLES_LSM6DSL_READER]` - Build configuration option `EXAMPLES_LSM6DSL_READER`
- `[Makefile:PROGNAME]` - Registers application/module target `lsm6dsl_reader`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `lsm6dsl_reader`
- `[lsm6dsl_reader_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_LSM6DSL]` - Requires kernel/app configuration `SENSORS_LSM6DSL`

## Side Effects
- `[lsm6dsl_reader_main.c:/dev/lsm6dsl0]` - Opens or interacts with VFS/device path `/dev/lsm6dsl0`
- `[lsm6dsl_reader_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[lsm6dsl_reader_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[lsm6dsl_reader_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
