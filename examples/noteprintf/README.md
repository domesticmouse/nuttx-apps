# noteprintf

## Overview
"Note printf!" example (`noteprintf`). Enable the "Note printf!" example

## Interface
- `[Kconfig:EXAMPLES_NOTEPRINTF]` - Build configuration option `EXAMPLES_NOTEPRINTF`
- `[Kconfig:EXAMPLES_NOTEPRINTF_PROGNAME]` - Build configuration option `EXAMPLES_NOTEPRINTF_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NOTEPRINTF_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NOTEPRINTF_PROGNAME}`
- `[noteprintf_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SCHED_INSTRUMENTATION_DUMP]` - Requires kernel/app configuration `SCHED_INSTRUMENTATION_DUMP`
- `[noteprintf_main.c:CONFIG_HAVE_FLOAT]` - Configuration guard on `CONFIG_HAVE_FLOAT`
- `[noteprintf_main.c:CONFIG_HAVE_DOUBLE]` - Configuration guard on `CONFIG_HAVE_DOUBLE`
- `[noteprintf_main.c:CONFIG_HAVE_LONG_DOUBLE]` - Configuration guard on `CONFIG_HAVE_LONG_DOUBLE`

## Side Effects
- None

## Verification
- Run: `make test`
