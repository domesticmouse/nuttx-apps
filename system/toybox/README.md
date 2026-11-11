# `system/toybox`

## Overview
Provides Toybox command suite (`system/toybox`). Download, patch and build Toybox (https://landley.net/toybox/), a 0BSD-licensed multi-call binary providing a POSIX/LSB command suite

## Interface
- [Makefile:PROGNAME=toybox]
- [Kconfig:CONFIG_SYSTEM_TOYBOX]
- [Kconfig:CONFIG_SYSTEM_TOYBOX_VERSION]
- [Kconfig:CONFIG_SYSTEM_TOYBOX_URL]
- [Kconfig:CONFIG_SYSTEM_TOYBOX_PRIORITY]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TOYBOX]: Build and feature compilation gated by `CONFIG_SYSTEM_TOYBOX`.
- [Kconfig:CONFIG_SYSTEM_TOYBOX_VERSION]: Build and feature compilation gated by `CONFIG_SYSTEM_TOYBOX_VERSION`.
- [Kconfig:depends on SCHED_WAITPID]: Requires Kconfig dependency condition `SCHED_WAITPID`.
- [Kconfig:depends on SCHED_HAVE_PARENT]: Requires Kconfig dependency condition `SCHED_HAVE_PARENT`.
- [Kconfig:depends on !DISABLE_PSEUDOFS_OPERATIONS]: Requires Kconfig dependency condition `!DISABLE_PSEUDOFS_OPERATIONS`.

## Side Effects
- None

## Verification
- Run: `make test`
