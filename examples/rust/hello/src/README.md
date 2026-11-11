# src

## Overview
NuttX `rust/hello/src` component implementing `lib.rs`.

## Interface
- `[lib.rs:hello_rust_cargo_main]` - Public Rust function `hello_rust_cargo_main()`
- `[lib.rs:struct Person]` - Rust struct `Person`

## Invariants
- `[lib.rs:unwrap]` - Panics if inner `Result`/`Option` operations return an error

## Side Effects
- `[lib.rs:println!]` - Prints formatted output to console

## Verification
- Run: `make test`
