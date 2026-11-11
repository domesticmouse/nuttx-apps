# `system/uniqueid`

## Overview
Provides 'uniqueid' command (`system/uniqueid`). Enable the uniqueid tool

## Interface
- [Makefile:PROGNAME=uniqueid]
- [Kconfig:CONFIG_SYSTEM_UNIQUEID]
- [uniqueid_main.c:struct cfg_s]
- [uniqueid_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_UNIQUEID]: Build and feature compilation gated by `CONFIG_SYSTEM_UNIQUEID`.
- [Kconfig:depends on BOARDCTL_UNIQUEID]: Requires Kconfig dependency condition `BOARDCTL_UNIQUEID`.

## Side Effects
- [uniqueid_main.c:malloc]: Allocates or releases dynamic heap memory.
- [uniqueid_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
