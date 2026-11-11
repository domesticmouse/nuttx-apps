# ws2812esp32rmt

## Overview
ws2812 Demo Program using ESP32_RMT (`ws2812esp32rmt`). Enable the ws2812 demo, using ESP32 RMT peripheral to generate the pulses

## Interface
- `[Kconfig:EXAMPLES_WS2812_ESP32_RMT]` - Build configuration option `EXAMPLES_WS2812_ESP32_RMT`
- `[Kconfig:EXAMPLES_WS2812_ESP32_RMT_PROGNAME]` - Build configuration option `EXAMPLES_WS2812_ESP32_RMT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WS2812_ESP32_RMT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_WS2812_ESP32_RMT_PROGNAME}`
- `[ws2812esp32rmt_main.c:struct led_s]` - Structure definition `led_s`
- `[ws2812esp32rmt_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ESP32_RMT]` - Requires kernel/app configuration `ESP32_RMT`
- `[ws2812esp32rmt_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[ws2812esp32rmt_main.c:/dev/rmt%d]` - Opens or interacts with VFS/device path `/dev/rmt%d`
- `[ws2812esp32rmt_main.c:open]` - Opens device nodes or files via `open()`
- `[ws2812esp32rmt_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[ws2812esp32rmt_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
