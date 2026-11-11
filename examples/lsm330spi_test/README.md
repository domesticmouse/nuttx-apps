# lsm330spi_test

## Overview
LSM330 SPI test program (`lsm330spi_test`). Enable the LSM330 sensor SPI test program.

## Interface
- `[Kconfig:EXAMPLES_LSM330SPI_TEST]` - Build configuration option `EXAMPLES_LSM330SPI_TEST`
- `[Kconfig:EXAMPLES_LSM330SPI_TEST_PROGNAME]` - Build configuration option `EXAMPLES_LSM330SPI_TEST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LSM330SPI_TEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LSM330SPI_TEST_PROGNAME}`
- `[lsm330spi_test_main.c:struct XYZ]` - Structure definition `XYZ`
- `[lsm330spi_test_main.c:lsm330acl_test]` - Public function `lsm330acl_test()`
- `[lsm330spi_test_main.c:lsm330gyro_test]` - Public function `lsm330gyro_test()`
- `[lsm330spi_test_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_LSM330SPI]` - Requires kernel/app configuration `SENSORS_LSM330SPI`
- `[lsm330spi_test_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[lsm330spi_test_main.c:open]` - Opens device nodes or files via `open()`
- `[lsm330spi_test_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[lsm330spi_test_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[lsm330spi_test_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
