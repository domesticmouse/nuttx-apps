# `system/grep`

## Overview
Provides system 'grep' command (`system/grep`). Enable support for the system 'grep' command (regex-based search).

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_GREP_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_GREP]
- [Kconfig:CONFIG_SYSTEM_GREP_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_GREP_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_GREP_STACKSIZE]
- [grep_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_GREP]: Build and feature compilation gated by `CONFIG_SYSTEM_GREP`.
- [Kconfig:CONFIG_SYSTEM_GREP_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_GREP_PROGNAME`.
- [Kconfig:depends on LIBC_REGEX]: Requires Kconfig dependency condition `LIBC_REGEX`.

## Side Effects
- [grep_main.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [grep_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
