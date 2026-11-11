# `system/gprof`

## Overview
Provides gprof tool (`system/gprof`). Enable support for the 'gprof' command.

## Interface
- [Makefile:PROGNAME=gprof]
- [Kconfig:CONFIG_SYSTEM_GPROF]
- [Kconfig:CONFIG_SYSTEM_GPROF_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_GPROF_STACKSIZE]
- [gprof.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_GPROF]: Build and feature compilation gated by `CONFIG_SYSTEM_GPROF`.
- [Kconfig:CONFIG_SYSTEM_GPROF_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_GPROF_PRIORITY`.
- [Kconfig:depends on !PROFILE_NONE || SIM_GPROF]: Requires Kconfig dependency condition `!PROFILE_NONE || SIM_GPROF`.
- [gprof.c:CONFIG_DISABLE_ENVIRON]: Conditional compilation gated by `CONFIG_DISABLE_ENVIRON`.

## Side Effects
- [gprof.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
