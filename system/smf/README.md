# `system/smf`

## Overview
Provides (SMF) support (`system/smf`). Enables the State Machine Framework (SMF) for implementing state machines

## Interface
- [Kconfig:CONFIG_SYSTEM_SMF]
- [Kconfig:CONFIG_SYSTEM_SMF_ANCESTOR_SUPPORT]
- [Kconfig:CONFIG_SYSTEM_SMF_INITIAL_TRANSITION]
- [smf.c:struct internal_ctx]
- [smf.c:smf_set_initial]
- [smf.c:smf_set_state]
- [smf.c:smf_set_terminate]
- [smf.c:smf_run_state]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SMF]: Build and feature compilation gated by `CONFIG_SYSTEM_SMF`.
- [Kconfig:CONFIG_SYSTEM_SMF_ANCESTOR_SUPPORT]: Build and feature compilation gated by `CONFIG_SYSTEM_SMF_ANCESTOR_SUPPORT`.
- [Kconfig:depends on SYSTEM_SMF_ANCESTOR_SUPPORT]: Requires Kconfig dependency condition `SYSTEM_SMF_ANCESTOR_SUPPORT`.
- [smf.c:CONFIG_SYSTEM_SMF_ANCESTOR_SUPPORT]: Conditional compilation gated by `CONFIG_SYSTEM_SMF_ANCESTOR_SUPPORT`.
- [smf.c:CONFIG_SYSTEM_SMF_INITIAL_TRANSITION]: Conditional compilation gated by `CONFIG_SYSTEM_SMF_INITIAL_TRANSITION`.

## Side Effects
- [smf.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
