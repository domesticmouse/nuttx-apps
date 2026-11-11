# usbserial

## Overview
USB serial test example (`usbserial`). Enable the USB serial test example

## Interface
- `[Kconfig:EXAMPLES_USBSERIAL]` - Build configuration option `EXAMPLES_USBSERIAL`
- `[Kconfig:EXAMPLES_USBSERIAL_BUFSIZE]` - Build configuration option `EXAMPLES_USBSERIAL_BUFSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `usbserial`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `usbserial`
- `[usbserial_main.c:main]` - Application entry point `main()`
- `[host.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on BOARDCTL]` - Requires kernel/app configuration `BOARDCTL`
- `[Kconfig:depends on USBDEV_TRACE || DEBUG_USB]` - Requires kernel/app configuration `USBDEV_TRACE || DEBUG_USB`
- `[Kconfig:depends on USBDEV_TRACE || DEBUG_USB]` - Requires kernel/app configuration `USBDEV_TRACE || DEBUG_USB`
- `[usbserial_main.c:#error]` - Compile-time precondition: Cannot define both CONFIG_EXAMPLES_USBSERIAL_INONLY and _OUTONLY
- `[usbserial_main.c:#error]` - Compile-time precondition: Cannot define both CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL and _ONLYBIG
- `[usbserial_main.c:CONFIG_CDCACM]` - Configuration guard on `CONFIG_CDCACM`
- `[usbserial_main.c:CONFIG_EXAMPLES_USBSERIAL_INONLY]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_INONLY`
- `[usbserial_main.c:CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL`
- `[usbserial_main.c:CONFIG_EXAMPLES_USBSERIAL_ONLYBIG]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_ONLYBIG`
- `[host.c:#error]` - Compile-time precondition: Cannot define both CONFIG_EXAMPLES_USBSERIAL_INONLY and _OUTONLY
- `[host.c:#error]` - Compile-time precondition: Cannot define both CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL and _ONLYBIG
- `[host.c:CONFIG_EXAMPLES_USBSERIAL_INONLY]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_INONLY`
- `[host.c:CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_ONLYSMALL`
- `[host.c:CONFIG_EXAMPLES_USBSERIAL_ONLYBIG]` - Configuration guard on `CONFIG_EXAMPLES_USBSERIAL_ONLYBIG`
- `[host.c:CONFIG_CDCACM]` - Configuration guard on `CONFIG_CDCACM`
- `[host.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[usbserial_main.c:/dev/ttyACM0]` - Opens or interacts with VFS/device path `/dev/ttyACM0`
- `[usbserial_main.c:/dev/ttyUSB0]` - Opens or interacts with VFS/device path `/dev/ttyUSB0`
- `[usbserial_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[usbserial_main.c:open]` - Opens device nodes or files via `open()`
- `[usbserial_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[usbserial_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[usbserial_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[host.c:/dev/ttyACM0]` - Opens or interacts with VFS/device path `/dev/ttyACM0`
- `[host.c:/dev/ttyUSB0]` - Opens or interacts with VFS/device path `/dev/ttyUSB0`
- `[host.c:open]` - Opens device nodes or files via `open()`
- `[host.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[host.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[host.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
