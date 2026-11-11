# `graphics/slcd`

## Overview
Provides Segment LCD Emulaton (`graphics/slcd`). Enable the CLcd class which implements an NX LCD simulation.

## Interface
- [Kconfig:CONFIG_GRAPHICS_SLCD]

## Invariants
- [Kconfig:CONFIG_GRAPHICS_SLCD]: Build and feature compilation gated by `CONFIG_GRAPHICS_SLCD`.
- [Kconfig:depends on NX && HAVE_CXX]: Requires Kconfig dependency condition `NX && HAVE_CXX`.

## Side Effects
- None

## Verification
- Run: `make test`
