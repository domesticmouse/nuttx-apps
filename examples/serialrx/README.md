# serialrx

## Overview
Serial RX example (`serialrx`). Enable the serial RX example

## Interface
- `[Kconfig:EXAMPLES_SERIALRX]` - Build configuration option `EXAMPLES_SERIALRX`
- `[Kconfig:EXAMPLES_SERIALRX_STACKSIZE]` - Build configuration option `EXAMPLES_SERIALRX_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `serialrx`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `serialrx`
- `[serialrx_main.c:main]` - Application entry point `main()`
- `[send.py:sys.argv]` - Command-line script taking target device path in `sys.argv[1]`

## Invariants
- `[serialrx_main.c:CONFIG_EXAMPLES_SERIALRX_BUFFERED]` - Configuration guard on `CONFIG_EXAMPLES_SERIALRX_BUFFERED`
- `[serialrx_main.c:CONFIG_EXAMPLES_SERIALRX_PRINTHYPHEN]` - Configuration guard on `CONFIG_EXAMPLES_SERIALRX_PRINTHYPHEN`
- `[serialrx_main.c:CONFIG_EXAMPLES_SERIALRX_PRINTHEX]` - Configuration guard on `CONFIG_EXAMPLES_SERIALRX_PRINTHEX`
- `[serialrx_main.c:CONFIG_EXAMPLES_SERIALRX_PRINTSTR]` - Configuration guard on `CONFIG_EXAMPLES_SERIALRX_PRINTSTR`
- `[serialrx_main.c:argc]` - Validates command-line argument count `argc`
- `[send.py:sys.argv]` - Requires `sys.argv[1]` path argument

## Side Effects
- `[serialrx_main.c:open]` - Opens device nodes or files via `open()`
- `[serialrx_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[serialrx_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[serialrx_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[send.py:open]` - Opens local file or serial device for reading/writing

## Verification
- Run: `make test`
