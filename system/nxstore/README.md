# `system/nxstore`

## Overview
Provides Nxstore LVGL App Store (`system/nxstore`). Enable the Nxstore LVGL graphical application store frontend. Lists packages from the local nxpkg repository, installs the

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NXSTORE_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NXSTORE]
- [Kconfig:CONFIG_SYSTEM_NXSTORE_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_NXSTORE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NXSTORE_STACKSIZE]
- [nxstore_main.c:enum install_state_e]
- [nxstore_main.c:struct install_ctx_s]
- [nxstore_main.c:struct running_app_s]
- [nxstore_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXSTORE]: Build and feature compilation gated by `CONFIG_SYSTEM_NXSTORE`.
- [Kconfig:CONFIG_SYSTEM_NXSTORE_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_NXSTORE_PROGNAME`.
- [Kconfig:depends on GRAPHICS_LVGL && SYSTEM_NXPKG && SCHED_WAITPID]: Requires Kconfig dependency condition `GRAPHICS_LVGL && SYSTEM_NXPKG && SCHED_WAITPID`.
- [Kconfig:depends on NETUTILS_CJSON]: Requires Kconfig dependency condition `NETUTILS_CJSON`.

## Side Effects
- [nxstore_main.c:mkdir]: Performs VFS file or device descriptor I/O operations.
- [nxstore_main.c:calloc]: Allocates or releases dynamic heap memory.
- [nxstore_main.c:posix_spawn]: Spawns child tasks, pthreads, or built-in applications.
- [nxstore_main.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
