# hidcombo

## Overview
USB HID keyboard + mouse combo example (`hidcombo`). Read a USB HID keyboard and a USB HID mouse at the same time from a single task using poll().  Useful to test keyboard + touchpad receivers, which expose both devices on the same USB device.

## Interface
- `[Kconfig:EXAMPLES_HIDCOMBO]` - Build configuration option `EXAMPLES_HIDCOMBO`
- `[Kconfig:EXAMPLES_HIDCOMBO_PROGNAME]` - Build configuration option `EXAMPLES_HIDCOMBO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HIDCOMBO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_HIDCOMBO_PROGNAME}`
- `[hidcombo_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on USBHOST_HIDKBD && USBHOST_HIDMOUSE && !HIDMOUSE_TSCIF]` - Requires kernel/app configuration `USBHOST_HIDKBD && USBHOST_HIDMOUSE && !HIDMOUSE_TSCIF`
- `[hidcombo_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[hidcombo_main.c:open]` - Opens device nodes or files via `open()`
- `[hidcombo_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[hidcombo_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
