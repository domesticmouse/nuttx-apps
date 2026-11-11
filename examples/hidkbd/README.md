# hidkbd

## Overview
USB HID keyboard example (`hidkbd`). Enable the USB HID keyboard example

## Interface
- `[Kconfig:EXAMPLES_HIDKBD]` - Build configuration option `EXAMPLES_HIDKBD`
- `[Kconfig:EXAMPLES_HIDKBD_PROGNAME]` - Build configuration option `EXAMPLES_HIDKBD_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HIDKBD_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_HIDKBD_PROGNAME}`
- `[hidkbd_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on USBHOST_HIDKBD]` - Requires kernel/app configuration `USBHOST_HIDKBD`
- `[Kconfig:depends on INPUT_KEYBOARD_BYTESTREAM]` - Requires kernel/app configuration `INPUT_KEYBOARD_BYTESTREAM`
- `[hidkbd_main.c:#error]` - Compile-time precondition: Interrupt endpoints are disabled (CONFIG_USBHOST_INT_DISABLE)
- `[hidkbd_main.c:CONFIG_EXAMPLES_HIDKBD_ENCODED]` - Configuration guard on `CONFIG_EXAMPLES_HIDKBD_ENCODED`
- `[hidkbd_main.c:CONFIG_USBHOST_INT_DISABLE]` - Configuration guard on `CONFIG_USBHOST_INT_DISABLE`
- `[hidkbd_main.c:CONFIG_EXAMPLES_HIDKBD_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_HIDKBD_DEVNAME`
- `[hidkbd_main.c:CONFIG_INPUT_KEYBOARD_BYTESTREAM]` - Configuration guard on `CONFIG_INPUT_KEYBOARD_BYTESTREAM`

## Side Effects
- `[hidkbd_main.c:/dev/kbda]` - Opens or interacts with VFS/device path `/dev/kbda`
- `[hidkbd_main.c:open]` - Opens device nodes or files via `open()`
- `[hidkbd_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[hidkbd_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[hidkbd_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
