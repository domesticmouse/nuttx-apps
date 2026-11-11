# media

## Overview
Media test (`media`). Enable the media test.  This test simply writes values onto the media hidden behind a character driver and verifies that the media can be successfully written and read.  This low level test is useful in the early phases of the bringup of a new block or mtd driver because it avoids the complexity of a file system.

## Interface
- `[Kconfig:EXAMPLES_MEDIA]` - Build configuration option `EXAMPLES_MEDIA`
- `[Kconfig:EXAMPLES_MEDIA_DEVPATH]` - Build configuration option `EXAMPLES_MEDIA_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MEDIA_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MEDIA_PROGNAME}`
- `[media_main.c:struct media_info_s]` - Structure definition `media_info_s`
- `[media_main.c:main]` - Application entry point `main()`

## Invariants
- `[media_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[media_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[media_main.c:open]` - Opens device nodes or files via `open()`
- `[media_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[media_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[media_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
