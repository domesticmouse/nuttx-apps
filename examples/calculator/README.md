# calculator

## Overview
Calculator (`calculator`). Enable the simple LVGL touchscreen calculator example.

## Interface
- `[Kconfig:EXAMPLES_CALCULATOR]` - Build configuration option `EXAMPLES_CALCULATOR`
- `[Kconfig:EXAMPLES_CALCULATOR_PRIORITY]` - Build configuration option `EXAMPLES_CALCULATOR_PRIORITY`
- `[Makefile:PROGNAME]` - Registers application/module target `calc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `calc`
- `[calculator_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on GRAPHICS_LVGL && INPUT_TOUCHSCREEN]` - Requires kernel/app configuration `GRAPHICS_LVGL && INPUT_TOUCHSCREEN`
- `[calculator_main.c:CONFIG_BOARDCTL_FINALINIT]` - Configuration guard on `CONFIG_BOARDCTL_FINALINIT`

## Side Effects
- `[calculator_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[calculator_main.c:sigaction]` - Registers signal handlers via `sigaction()`

## Verification
- Run: `make test`
