# src

## Overview
NuttX `rust/slint/src` component implementing `lib.rs`.

## Interface
- `[lib.rs:slint_main]` - Public Rust function `slint_main()`
- `[lib.rs:struct NuttXPlatform]` - Rust struct `NuttXPlatform`
- `[lib.rs:struct NuttXRenderer]` - Rust struct `NuttXRenderer`

## Invariants
- `[lib.rs:unwrap]` - Panics if inner `Result`/`Option` operations return an error

## Side Effects
- `[lib.rs:/dev/fb0\0]` - Accesses device node `/dev/fb0\0`
- `[lib.rs:/dev/input0\0]` - Accesses device node `/dev/input0\0`
- `[lib.rs:println!]` - Prints formatted output to console

## Verification
- Run: `make test`
