# hx711

## Overview
HX711 driver example (`hx711`). Enable the HX711 example. This program is also useful during development as it's possible to manipulate and dump hx711 settings, as well as print conversions to terminal.

## Interface
- `[Kconfig:EXAMPLES_HX711]` - Build configuration option `EXAMPLES_HX711`
- `[Kconfig:EXAMPLES_HX711_PROGNAME]` - Build configuration option `EXAMPLES_HX711_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HX711_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_HX711_PROGNAME}`
- `[hx711_main.c:struct hx711_config]` - Structure definition `hx711_config`
- `[hx711_main.c:hx711_set_options]` - Public function `hx711_set_options()`
- `[hx711_main.c:main]` - Application entry point `main()`
- `[hx711_main.c:getopt]` - Command-line option parser supporting flags `"hd:Dt:a:c:g:r:v:s"`

## Invariants
- None

## Side Effects
- `[hx711_main.c:/dev/hx711_0]` - Opens or interacts with VFS/device path `/dev/hx711_0`
- `[hx711_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[hx711_main.c:open]` - Opens device nodes or files via `open()`
- `[hx711_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[hx711_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
