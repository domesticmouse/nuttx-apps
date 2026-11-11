# termios

## Overview
Termios example (`termios`). Enable the Termios example. This example shows how to change serial parameters like baud rate, stop bits, data length and parity using the termios interface.

## Interface
- `[Kconfig:EXAMPLES_TERMIOS]` - Build configuration option `EXAMPLES_TERMIOS`
- `[Kconfig:EXAMPLES_TERMIOS_PRIORITY]` - Build configuration option `EXAMPLES_TERMIOS_PRIORITY`
- `[Makefile:PROGNAME]` - Registers application/module target `termios`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `termios`
- `[termios_main.c:main]` - Application entry point `main()`

## Invariants
- `[termios_main.c:CONFIG_EXAMPLES_TERMIOS_DIS_HW_FC]` - Configuration guard on `CONFIG_EXAMPLES_TERMIOS_DIS_HW_FC`

## Side Effects
- `[termios_main.c:/dev/ttyS0]` - Opens or interacts with VFS/device path `/dev/ttyS0`
- `[termios_main.c:open]` - Opens device nodes or files via `open()`
- `[termios_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
