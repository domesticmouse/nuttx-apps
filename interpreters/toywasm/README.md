# `interpreters/toywasm`

## Overview
Implements Toywasm Webassembly Runtime (`interpreters/toywasm`) for the NuttX application subsystem.

## Interface
- [Makefile:PROGNAME=toywasm]
- [Kconfig:CONFIG_INTERPRETERS_TOYWASM]
- [Kconfig:CONFIG_INTERPRETERS_TOYWASM_PRIORITY]
- [Kconfig:CONFIG_INTERPRETERS_TOYWASM_STACKSIZE]
- [regen.sh]
- `include`: [./include/README.md](./include/README.md) - Implements `interpreters/toywasm/include` source and header components (`toywasm_config.h`, `toywasm_version.h`) in the NuttX application tree.
- `src`: [./src/README.md](./src/README.md) - Implements `interpreters/toywasm/src` source and header components (`toywasm_config.c`) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_TOYWASM]: Build and feature compilation gated by `CONFIG_INTERPRETERS_TOYWASM`.
- [Kconfig:CONFIG_INTERPRETERS_TOYWASM_PRIORITY]: Build and feature compilation gated by `CONFIG_INTERPRETERS_TOYWASM_PRIORITY`.
- [Kconfig:depends on !DISABLE_PTHREAD]: Requires Kconfig dependency condition `!DISABLE_PTHREAD`.

## Side Effects
- [regen.sh]: Executes shell utilities and generates or modifies build artifacts.

## Verification
- Run: `make test`
