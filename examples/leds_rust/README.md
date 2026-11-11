# leds_rust

## Overview
"LEDs Rust" example (`leds_rust`). Enable the "LEDs Rust" example

## Interface
- `[Kconfig:EXAMPLES_LEDS_RUST]` - Build configuration option `EXAMPLES_LEDS_RUST`
- `[Kconfig:EXAMPLES_LEDS_RUST_PROGNAME]` - Build configuration option `EXAMPLES_LEDS_RUST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LEDS_RUST_PROGNAME)`
- `[leds_rust_main.rs:leds_rust_main]` - Public Rust function `leds_rust_main()`
- `[leds_rust_main.rs:main]` - Rust entry point `main()`
- `[nuttx.rs:printf]` - Public Rust function `printf()`
- `[nuttx.rs:open]` - Public Rust function `open()`
- `[nuttx.rs:close]` - Public Rust function `close()`
- `[nuttx.rs:ioctl]` - Public Rust function `ioctl()`
- `[nuttx.rs:usleep]` - Public Rust function `usleep()`
- `[nuttx.rs:puts]` - Public Rust function `puts()`
- `[nuttx.rs:safe_open]` - Public Rust function `safe_open()`
- `[nuttx.rs:safe_ioctl]` - Public Rust function `safe_ioctl()`
- `[nuttx.rs:safe_puts]` - Public Rust function `safe_puts()`

## Invariants
- `[Kconfig:depends on USERLED]` - Requires kernel/app configuration `USERLED`
- `[leds_rust_main.rs:#![no_std]]` - Compiles without the Rust standard library (`no_std`)

## Side Effects
- `[leds_rust_main.rs:/dev/userleds]` - Accesses device node `/dev/userleds`
- `[leds_rust_main.rs:ioctl]` - Invokes NuttX C `ioctl()` FFI bindings
- `[leds_rust_main.rs:println!]` - Prints formatted output to console
- `[nuttx.rs:ioctl]` - Invokes NuttX C `ioctl()` FFI bindings
- `[nuttx.rs:println!]` - Prints formatted output to console

## Verification
- Run: `make test`
