# pmstress

## Overview
Power management current staircase (`pmstress`). Walk the power management states in a fixed, timed sequence, so that a logging supply can record the current of each state with nothing attached to the board.  The deepest state comes last and is held until the board is powered off.

## Interface
- `[Kconfig:EXAMPLES_PMSTRESS]` - Build configuration option `EXAMPLES_PMSTRESS`
- `[Kconfig:EXAMPLES_PMSTRESS_PROGNAME]` - Build configuration option `EXAMPLES_PMSTRESS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_PMSTRESS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_PMSTRESS_PROGNAME}`
- `[pmstress_main.c:struct pmstress_step_s]` - Structure definition `pmstress_step_s`
- `[pmstress_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PM]` - Requires kernel/app configuration `PM`
- `[Kconfig:depends on USERLED_LOWER]` - Requires kernel/app configuration `USERLED_LOWER`
- `[pmstress_main.c:CONFIG_ARCH_CHIP_RP23XX]` - Configuration guard on `CONFIG_ARCH_CHIP_RP23XX`
- `[pmstress_main.c:CONFIG_RTC_DRIVER]` - Configuration guard on `CONFIG_RTC_DRIVER`
- `[pmstress_main.c:CONFIG_USERLED_LOWER]` - Configuration guard on `CONFIG_USERLED_LOWER`
- `[pmstress_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[pmstress_main.c:/dev/rtc0]` - Opens or interacts with VFS/device path `/dev/rtc0`
- `[pmstress_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[pmstress_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[pmstress_main.c:open]` - Opens device nodes or files via `open()`
- `[pmstress_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
