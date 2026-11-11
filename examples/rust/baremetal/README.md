# baremetal

## Overview
"Hello, Rust!" example (`rust/baremetal`). Enable the "Hello, Rust!" example to show how to build and run a baremetal Rust application with rustc.

## Interface
- `[Kconfig:EXAMPLES_HELLO_RUST]` - Build configuration option `EXAMPLES_HELLO_RUST`
- `[Kconfig:EXAMPLES_HELLO_RUST_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_RUST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_RUST_PROGNAME)`
- `[hello_rust_main.rs:printf]` - Public Rust function `printf()`
- `[hello_rust_main.rs:hello_rust_main]` - Public Rust function `hello_rust_main()`

## Invariants
- `[hello_rust_main.rs:#![no_std]]` - Compiles without the Rust standard library (`no_std`)

## Side Effects
- `[hello_rust_main.rs:println!]` - Prints formatted output to console

## Verification
- Run: `make test`
