# capture

## Overview
PWM Capture example (`capture`). Enable the pwm capture example

## Interface
- `[Kconfig:EXAMPLES_CAPTURE]` - Build configuration option `EXAMPLES_CAPTURE`
- `[Kconfig:EXAMPLES_CAPTURE_DEVPATH]` - Build configuration option `EXAMPLES_CAPTURE_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `cap`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `cap`
- `[cap.h:struct cap_example_s]` - Structure definition `cap_example_s`
- `[cap_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on CAPTURE]` - Requires kernel/app configuration `CAPTURE`
- `[cap_main.c:CONFIG_CAPTURE_NOTIFY]` - Configuration guard on `CONFIG_CAPTURE_NOTIFY`

## Side Effects
- `[cap_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[cap_main.c:open]` - Opens device nodes or files via `open()`
- `[cap_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
