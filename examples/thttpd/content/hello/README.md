# hello

## Overview
NuttX `thttpd/content/hello` component: Public Functions

## Interface
- `[hello.c:hello_main]` - Application entry point `hello_main()`

## Invariants
- `[hello.c:CONFIG_THTTPD_BINFS]` - Configuration guard on `CONFIG_THTTPD_BINFS`

## Side Effects
- `[hello.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
