# txmorse

## Overview
txmorse (Morse code transmitter) (`txmorse`). Enable the Morse code transmission example.

## Interface
- `[Kconfig:EXAMPLES_TXMORSE]` - Build configuration option `EXAMPLES_TXMORSE`
- `[Kconfig:EXAMPLES_TXMORSE_PROGNAME]` - Build configuration option `EXAMPLES_TXMORSE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TXMORSE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TXMORSE_PROGNAME}`
- `[txmorse_main.c:main]` - Application entry point `main()`
- `[txmorse_main.c:getopt]` - Command-line option parser supporting flags `":hd:"`

## Invariants
- `[Kconfig:depends on AUDIOUTILS_MORSEY]` - Requires kernel/app configuration `AUDIOUTILS_MORSEY`
- `[txmorse_main.c:CONFIG_DEV_GPIO]` - Configuration guard on `CONFIG_DEV_GPIO`

## Side Effects
- `[txmorse_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[txmorse_main.c:open]` - Opens device nodes or files via `open()`

## Verification
- Run: `make test`
