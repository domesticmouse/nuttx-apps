# slint

## Overview
Slint Basic Example (`rust/slint`). Enable the basic Slint example.

## Interface
- `[Kconfig:EXAMPLES_RUST_SLINT]` - Build configuration option `EXAMPLES_RUST_SLINT`
- `[Kconfig:EXAMPLES_RUST_SLINT_PROGNAME]` - Build configuration option `EXAMPLES_RUST_SLINT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_RUST_SLINT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `CRATE_NAME`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_RUST_SLINT_PROGNAME}`
- `[build.rs:main]` - Rust entry point `main()`
- **src**: [`./src/README.md`](./src/README.md) - NuttX `rust/slint/src` component implementing `lib.rs`.

## Invariants
- `[build.rs:unwrap]` - Panics if inner `Result`/`Option` operations return an error

## Side Effects
- `[build.rs:compile_with_config]` - Compiles `.slint` UI definitions into Rust code at build time

## Verification
- Run: `make test`
