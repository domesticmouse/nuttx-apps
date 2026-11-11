# stepper

## Overview
Stepper controller test (`stepper`). Enable the stepper controller test

## Interface
- `[Kconfig:EXAMPLES_STEPPER]` - Build configuration option `EXAMPLES_STEPPER`
- `[Makefile:PROGNAME]` - Registers application/module target `stepper`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `stepper`
- `[stepper.c:struct stepper_args]` - Structure definition `stepper_args`
- `[stepper.c:main]` - Application entry point `main()`

## Invariants
- `[stepper.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[stepper.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[stepper.c:open]` - Opens device nodes or files via `open()`
- `[stepper.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[stepper.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[stepper.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
