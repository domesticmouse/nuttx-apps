# ws2812

## Overview
ws2812 Demo Program (`ws2812`). Enable the ws2812 demo

## Interface
- `[Kconfig:EXAMPLES_WS2812]` - Build configuration option `EXAMPLES_WS2812`
- `[Kconfig:EXAMPLES_WS2812_PROGNAME]` - Build configuration option `EXAMPLES_WS2812_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WS2812_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_WS2812_PROGNAME}`
- `[ws2812_main.c:struct neo_config_s]` - Structure definition `neo_config_s`
- `[ws2812_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on WS2812]` - Requires kernel/app configuration `WS2812`

## Side Effects
- `[ws2812_main.c:open]` - Opens device nodes or files via `open()`
- `[ws2812_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[ws2812_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
