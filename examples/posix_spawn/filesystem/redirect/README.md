# redirect

## Overview
NuttX `posix_spawn/filesystem/redirect` component: Public Functions

## Interface
- `[redirect.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[redirect.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
