# `system/gcov`

## Overview
Provides gcov tool (`system/gcov`). Enable support for the 'gcov' command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_GCOV_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_GCOV]
- [Kconfig:CONFIG_SYSTEM_GCOV_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_GCOV_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_GCOV_STACKSIZE]
- [gcov.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_GCOV]: Build and feature compilation gated by `CONFIG_SYSTEM_GCOV`.
- [Kconfig:CONFIG_SYSTEM_GCOV_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_GCOV_PROGNAME`.
- [Kconfig:depends on !COVERAGE_NONE]: Requires Kconfig dependency condition `!COVERAGE_NONE`.

## Side Effects
- [gcov.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
