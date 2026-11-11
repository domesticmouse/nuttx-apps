# qencoder

## Overview
Quadrature encoder example (`qencoder`). Enable the quadrature encoder example

## Interface
- `[Kconfig:EXAMPLES_QENCODER]` - Build configuration option `EXAMPLES_QENCODER`
- `[Kconfig:EXAMPLES_QENCODER_DEVPATH]` - Build configuration option `EXAMPLES_QENCODER_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `qe`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `qe`
- `[qe.h:struct qe_example_s]` - Structure definition `qe_example_s`
- `[qe_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_QENCODER]` - Requires kernel/app configuration `SENSORS_QENCODER`
- `[Kconfig:depends on EXAMPLES_QENCODER_HAVE_MAXPOS]` - Requires kernel/app configuration `EXAMPLES_QENCODER_HAVE_MAXPOS`
- `[qe_main.c:#error]` - Compile-time precondition: CONFIG_EXAMPLES_QENCODER_MAXPOS not specified
- `[qe_main.c:CONFIG_EXAMPLES_QENCODER_HAVE_MAXPOS]` - Configuration guard on `CONFIG_EXAMPLES_QENCODER_HAVE_MAXPOS`
- `[qe_main.c:CONFIG_EXAMPLES_QENCODER_MAXPOS]` - Configuration guard on `CONFIG_EXAMPLES_QENCODER_MAXPOS`

## Side Effects
- `[qe_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[qe_main.c:open]` - Opens device nodes or files via `open()`
- `[qe_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
