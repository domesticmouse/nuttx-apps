# lsm303_reader

## Overview
LSM303 reader example (`lsm303_reader`). Enable the LSM303 reader example

## Interface
- `[Kconfig:EXAMPLES_LSM303_READER]` - Build configuration option `EXAMPLES_LSM303_READER`
- `[Makefile:PROGNAME]` - Registers application/module target `lsm303_reader`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `lsm303_reader`
- `[lsm303_reader_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_LSM303AGR]` - Requires kernel/app configuration `SENSORS_LSM303AGR`

## Side Effects
- `[lsm303_reader_main.c:/dev/lsm303agr0]` - Opens or interacts with VFS/device path `/dev/lsm303agr0`
- `[lsm303_reader_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[lsm303_reader_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[lsm303_reader_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
