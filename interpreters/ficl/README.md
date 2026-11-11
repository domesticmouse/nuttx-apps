# `interpreters/ficl`

## Overview
Provides Ficl Forth interpreter (`interpreters/ficl`). Enable support for the Ficl interpreter interpreter. See README.txt file in the apps/interpreters/ficl directory. Use of this configuration assumes

## Interface
- [Kconfig:CONFIG_INTERPRETERS_FICL]
- [configure.sh]
- `src`: [./src/README.md](./src/README.md) - Implements `interpreters/ficl/src` source and header components (`nuttx.c`, `nuttx.h`) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_FICL]: Build and feature compilation gated by `CONFIG_INTERPRETERS_FICL`.

## Side Effects
- [configure.sh]: Executes shell utilities and generates or modifies build artifacts.

## Verification
- Run: `make test`
