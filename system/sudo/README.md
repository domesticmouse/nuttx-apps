# `system/sudo`

## Overview
Provides sudo (setuid privilege helper) (`system/sudo`). Install a Linux-style setuid-root ``sudo`` program. The kernel raises the effective UID to zero when the ELF is loaded (see

## Interface
- [Makefile:PROGNAME=sudo]
- [Kconfig:CONFIG_SYSTEM_SUDO]
- [Kconfig:CONFIG_SYSTEM_SUDO_SUDOERS_PATH]
- [Kconfig:CONFIG_SYSTEM_SUDO_ALLOWED_USERS]
- [sudo_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SUDO]: Build and feature compilation gated by `CONFIG_SYSTEM_SUDO`.
- [Kconfig:CONFIG_SYSTEM_SUDO_SUDOERS_PATH]: Build and feature compilation gated by `CONFIG_SYSTEM_SUDO_SUDOERS_PATH`.
- [Kconfig:depends on SCHED_USER_IDENTITY]: Requires Kconfig dependency condition `SCHED_USER_IDENTITY`.
- [Kconfig:depends on LIBC_PASSWD_FILE]: Requires Kconfig dependency condition `LIBC_PASSWD_FILE`.
- [Kconfig:depends on FSUTILS_PASSWD]: Requires Kconfig dependency condition `FSUTILS_PASSWD`.

## Side Effects
- [sudo_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [sudo_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
