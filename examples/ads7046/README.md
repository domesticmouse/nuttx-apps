# ads7046

## Overview
ADS7046 ADC example (`ads7046`). Enable the ADS7046 example

## Interface
- `[Kconfig:EXAMPLES_ADS7046]` - Build configuration option `EXAMPLES_ADS7046`
- `[Kconfig:EXAMPLES_ADS7046_PROGNAME]` - Build configuration option `EXAMPLES_ADS7046_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ADS7046_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ADS7046_PROGNAME}`
- `[ads7046_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ADC_ADS7046]` - Requires kernel/app configuration `ADC_ADS7046`

## Side Effects
- `[ads7046_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[ads7046_main.c:open]` - Opens device nodes or files via `open()`
- `[ads7046_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
