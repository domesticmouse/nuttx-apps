# calib_udelay

## Overview
Calibration tool for udelay (`calib_udelay`). Note that libm support is also required by this tool.  You may select CONFIG_LIBM to use the NuttX libm if you are not using an external libm.

## Interface
- `[Kconfig:EXAMPLES_CALIB_UDELAY]` - Build configuration option `EXAMPLES_CALIB_UDELAY`
- `[Kconfig:EXAMPLES_CALIB_UDELAY_NUM_MEASUREMENTS]` - Build configuration option `EXAMPLES_CALIB_UDELAY_NUM_MEASUREMENTS`
- `[Makefile:PROGNAME]` - Registers application/module target `calib_udelay`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `calib_udelay`
- `[calib_udelay_main.c:struct measurement_s]` - Structure definition `measurement_s`
- `[calib_udelay_main.c:main]` - Application entry point `main()`

## Invariants
- `[calib_udelay_main.c:CONFIG_EXAMPLES_CALIB_UDELAY_NUM_MEASUREMENTS]` - Configuration guard on `CONFIG_EXAMPLES_CALIB_UDELAY_NUM_MEASUREMENTS`
- `[calib_udelay_main.c:CONFIG_EXAMPLES_CALIB_UDELAY_NUM_RESULTS]` - Configuration guard on `CONFIG_EXAMPLES_CALIB_UDELAY_NUM_RESULTS`

## Side Effects
- `[calib_udelay_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
