# popen

## Overview
popen() example (`popen`). Enable the popen() example

## Interface
- `[Kconfig:EXAMPLES_POPEN]` - Build configuration option `EXAMPLES_POPEN`
- `[Kconfig:EXAMPLES_POPEN_PROGNAME]` - Build configuration option `EXAMPLES_POPEN_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_POPEN_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_POPEN_PROGNAME}`
- `[popen_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PIPES && LIBC_EXECFUNCS && SCHED_WAITPID]` - Requires kernel/app configuration `PIPES && LIBC_EXECFUNCS && SCHED_WAITPID`
- `[Kconfig:depends on !DISABLE_POSIX_TIMERS]` - Requires kernel/app configuration `!DISABLE_POSIX_TIMERS`
- `[popen_main.c:CONFIG_SIG_EVTHREAD]` - Configuration guard on `CONFIG_SIG_EVTHREAD`

## Side Effects
- `[popen_main.c:timer_create]` - Creates POSIX interval timers via `timer_create()`
- `[popen_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
