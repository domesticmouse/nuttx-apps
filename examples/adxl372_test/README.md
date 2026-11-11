# adxl372_test

## Overview
ADXL372 test program (`adxl372_test`). Enable the ADXL372 sensor SPI test program.

## Interface
- `[Kconfig:EXAMPLES_ADXL372_TEST]` - Build configuration option `EXAMPLES_ADXL372_TEST`
- `[Kconfig:EXAMPLES_ADXL372_TEST_PROGNAME]` - Build configuration option `EXAMPLES_ADXL372_TEST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ADXL372_TEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ADXL372_TEST_PROGNAME}`
- `[adxl372_test_main.c:struct XYZ]` - Structure definition `XYZ`
- `[adxl372_test_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_ADXL372]` - Requires kernel/app configuration `SENSORS_ADXL372`
- `[adxl372_test_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[adxl372_test_main.c:open]` - Opens device nodes or files via `open()`
- `[adxl372_test_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[adxl372_test_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[adxl372_test_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
