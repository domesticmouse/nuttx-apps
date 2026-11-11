# telnetd

## Overview
Telnet daemon example (`telnetd`). Enable the Telnet daemon example

## Interface
- `[Kconfig:EXAMPLES_TELNETD]` - Build configuration option `EXAMPLES_TELNETD`
- `[Kconfig:EXAMPLES_TELNETD_NOMAC]` - Build configuration option `EXAMPLES_TELNETD_NOMAC`
- `[Makefile:PROGNAME]` - Registers application/module target `example_telnetd`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `example_telnetd`
- `[telnetd.c:struct ptentry_s]` - Structure definition `ptentry_s`
- `[telnetd.c:telnetd_session]` - Public function `telnetd_session()`
- `[telnetd.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_TELNETD]` - Requires kernel/app configuration `NETUTILS_TELNETD`
- `[telnetd.h:CONFIG_EXAMPLES_TELNETD_DAEMONPRIO]` - Configuration guard on `CONFIG_EXAMPLES_TELNETD_DAEMONPRIO`
- `[telnetd.h:CONFIG_EXAMPLES_TELNETD_DAEMONSTACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_TELNETD_DAEMONSTACKSIZE`
- `[telnetd.h:CONFIG_EXAMPLES_TELNETD_CLIENTPRIO]` - Configuration guard on `CONFIG_EXAMPLES_TELNETD_CLIENTPRIO`
- `[telnetd.h:CONFIG_EXAMPLES_TELNETD_CLIENTSTACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_TELNETD_CLIENTSTACKSIZE`
- `[telnetd.c:CONFIG_BOARDCTL_RESET]` - Configuration guard on `CONFIG_BOARDCTL_RESET`
- `[telnetd.c:CONFIG_EXAMPLES_TELNETD_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_TELNETD_NOMAC`

## Side Effects
- `[telnetd.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[telnetd.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
