# xbc_test

## Overview
XBox Controller Test example (`xbc_test`). Enable the XBox Controller Test example

## Interface
- `[Kconfig:EXAMPLES_XBC_TEST]` - Build configuration option `EXAMPLES_XBC_TEST`
- `[Kconfig:EXAMPLES_XBC_TEST_PROGNAME]` - Build configuration option `EXAMPLES_XBC_TEST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_XBC_TEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_XBC_TEST_PROGNAME}`
- `[xbc_test_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on USBHOST]` - Requires kernel/app configuration `USBHOST`
- `[Kconfig:depends on !USBHOST_INT_DISABLE]` - Requires kernel/app configuration `!USBHOST_INT_DISABLE`
- `[xbc_test_main.c:CONFIG_EXAMPLES_XBC_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_XBC_DEVNAME`

## Side Effects
- `[xbc_test_main.c:/dev/xboxa]` - Opens or interacts with VFS/device path `/dev/xboxa`
- `[xbc_test_main.c:open]` - Opens device nodes or files via `open()`
- `[xbc_test_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[xbc_test_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
