# pulsecount

## Overview
pulsecount example (`pulsecount`). Enable the finite pulsecount example

## Interface
- `[Kconfig:EXAMPLES_PULSECOUNT]` - Build configuration option `EXAMPLES_PULSECOUNT`
- `[Kconfig:EXAMPLES_PULSECOUNT_DEVPATH]` - Build configuration option `EXAMPLES_PULSECOUNT_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `pulsecount`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pulsecount`
- `[pulsecount_main.c:struct pulsecount_state_s]` - Structure definition `pulsecount_state_s`
- `[pulsecount_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PULSECOUNT]` - Requires kernel/app configuration `PULSECOUNT`

## Side Effects
- `[pulsecount_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[pulsecount_main.c:open]` - Opens device nodes or files via `open()`
- `[pulsecount_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
