# serloop

## Overview
Serial loopback example (`serloop`). Enable the serial loopback example

## Interface
- `[Kconfig:EXAMPLES_SERLOOP]` - Build configuration option `EXAMPLES_SERLOOP`
- `[Makefile:PROGNAME]` - Registers application/module target `serloop`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `serloop`
- `[serloop_main.c:main]` - Application entry point `main()`

## Invariants
- `[serloop_main.c:CONFIG_EXAMPLES_SERLOOP_BUFIO]` - Configuration guard on `CONFIG_EXAMPLES_SERLOOP_BUFIO`

## Side Effects
- `[serloop_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[serloop_main.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
