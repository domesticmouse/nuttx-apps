# lis3dsh_reader

## Overview
LIS3DSH acceleration reader example (`lis3dsh_reader`). Enable the LIS3DSH reader example

## Interface
- `[Kconfig:EXAMPLES_LIS3DSH_READER]` - Build configuration option `EXAMPLES_LIS3DSH_READER`
- `[Kconfig:EXAMPLES_LIS3DSH_READER_PROGNAME]` - Build configuration option `EXAMPLES_LIS3DSH_READER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LIS3DSH_READER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LIS3DSH_READER_PROGNAME}`
- `[lis3dsh_reader_main.c:struct acc_data_t]` - Structure definition `acc_data_t`
- `[lis3dsh_reader_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LIS3DSH]` - Requires kernel/app configuration `LIS3DSH`
- `[Kconfig:depends on SPI_EXCHANGE]` - Requires kernel/app configuration `SPI_EXCHANGE`

## Side Effects
- `[lis3dsh_reader_main.c:/dev/acc0]` - Opens or interacts with VFS/device path `/dev/acc0`
- `[lis3dsh_reader_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[lis3dsh_reader_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
