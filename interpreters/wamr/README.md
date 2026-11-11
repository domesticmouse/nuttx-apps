# `interpreters/wamr`

## Overview
Provides Webassembly Micro Runtime (`interpreters/wamr`). Version WAMR-09-29-2020 and later (include main) supported.

## Interface
- [Makefile:PROGNAME=iwasm]
- [Kconfig:CONFIG_INTERPRETERS_WAMR]
- [Kconfig:CONFIG_INTERPRETERS_WAMR_VERSION]
- [Kconfig:CONFIG_INTERPRETERS_IWASM_TASK]
- [Kconfig:CONFIG_INTERPRETERS_WAMR_PRIORITY]
- [wamr_custom_init.c:wamr_custom_init]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_WAMR]: Build and feature compilation gated by `CONFIG_INTERPRETERS_WAMR`.
- [Kconfig:CONFIG_INTERPRETERS_WAMR_VERSION]: Build and feature compilation gated by `CONFIG_INTERPRETERS_WAMR_VERSION`.
- [Kconfig:depends on INTERPRETERS_WAMR_AOT]: Requires Kconfig dependency condition `INTERPRETERS_WAMR_AOT`.
- [Kconfig:depends on INTERPRETERS_WAMR_CLASSIC]: Requires Kconfig dependency condition `INTERPRETERS_WAMR_CLASSIC`.
- [Kconfig:depends on INTERPRETERS_WAMR_THREAD_MGR]: Requires Kconfig dependency condition `INTERPRETERS_WAMR_THREAD_MGR`.
- [wamr_custom_init.c:CONFIG_INTERPRETERS_WAMR_EXTERNAL_MODULE_REGISTRY]: Conditional compilation gated by `CONFIG_INTERPRETERS_WAMR_EXTERNAL_MODULE_REGISTRY`.

## Side Effects
- None

## Verification
- Run: `make test`
