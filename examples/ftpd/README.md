# ftpd

## Overview
FTP server example (`ftpd`). Enable the FTP server example

## Interface
- `[Kconfig:EXAMPLES_FTPD]` - Build configuration option `EXAMPLES_FTPD`
- `[Kconfig:EXAMPLES_FTPD_PORT]` - Build configuration option `EXAMPLES_FTPD_PORT`
- `[Makefile:PROGNAME]` - Registers application/module target `ftpd_start ftpd_stop`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `ftpd_start`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `ftpd_stop`
- `[ftpd.h:struct fptd_account_s]` - Structure definition `fptd_account_s`
- `[ftpd.h:struct ftpd_globals_s]` - Structure definition `ftpd_globals_s`
- `[ftpd_main.c:ftpd_daemon]` - Public function `ftpd_daemon()`
- `[ftpd_main.c:main]` - Application entry point `main()`
- `[ftpd_main.c:ftpd_stop_main]` - Application entry point `ftpd_stop_main()`
- `[ftpd_main.c:getopt]` - Command-line option parser supporting flags `"46"`

## Invariants
- `[ftpd.h:CONFIG_EXAMPLES_FTPD_PRIO]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_PRIO`
- `[ftpd.h:CONFIG_EXAMPLES_FTPD_STACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_STACKSIZE`
- `[ftpd.h:CONFIG_EXAMPLES_FTPD_CLIENTPRIO]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_CLIENTPRIO`
- `[ftpd.h:CONFIG_EXAMPLES_FTPD_CLIENTSTACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_CLIENTSTACKSIZE`
- `[ftpd_main.c:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[ftpd_main.c:CONFIG_EXAMPLES_FTPD_NONETINIT]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_NONETINIT`
- `[ftpd_main.c:CONFIG_EXAMPLES_FTPD_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_FTPD_NOMAC`

## Side Effects
- `[ftpd_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[ftpd_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
