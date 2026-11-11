# hts221_reader

## Overview
HTS221 reader example (`hts221_reader`). Enable the HTS221 reader example

## Interface
- `[Kconfig:EXAMPLES_HTS221_READER]` - Build configuration option `EXAMPLES_HTS221_READER`
- `[Makefile:PROGNAME]` - Registers application/module target `hts221_reader`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `hts221_reader`
- `[hts221_reader_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_HTS221]` - Requires kernel/app configuration `SENSORS_HTS221`

## Side Effects
- `[hts221_reader_main.c:/dev/hts2210]` - Opens or interacts with VFS/device path `/dev/hts2210`
- `[hts221_reader_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[hts221_reader_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[hts221_reader_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
