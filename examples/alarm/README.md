# alarm

## Overview
RTC alarm driver example (`alarm`). Enable the RTC driver alarm test

## Interface
- `[Kconfig:EXAMPLES_ALARM]` - Build configuration option `EXAMPLES_ALARM`
- `[Kconfig:EXAMPLES_ALARM_PROGNAME]` - Build configuration option `EXAMPLES_ALARM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ALARM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ALARM_PROGNAME}`
- `[alarm_main.c:main]` - Application entry point `main()`
- `[alarm_main.c:getopt]` - Command-line option parser supporting flags `":a:cr"`

## Invariants
- `[Kconfig:depends on RTC_DRIVER && RTC_ALARM]` - Requires kernel/app configuration `RTC_DRIVER && RTC_ALARM`

## Side Effects
- `[alarm_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[alarm_main.c:open]` - Opens device nodes or files via `open()`
- `[alarm_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[alarm_main.c:sigaction]` - Registers signal handlers via `sigaction()`
- `[alarm_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
