# `industry/abnt_codi`

## Overview
Provides ABNT CODI Library (`industry/abnt_codi`). Enable or disable the ABNT CODI Library

## Interface
- [Kconfig:CONFIG_INDUSTRY_ABNT_CODI_LIB]
- [abnt_codi.c:abnt_codi_checksum]
- [abnt_codi.c:abnt_codi_parse]

## Invariants
- [Kconfig:CONFIG_INDUSTRY_ABNT_CODI_LIB]: Build and feature compilation gated by `CONFIG_INDUSTRY_ABNT_CODI_LIB`.

## Side Effects
- [abnt_codi.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
