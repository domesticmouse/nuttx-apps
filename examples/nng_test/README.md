# nng_test

## Overview
NNG pubsub program (`nng_test`). Enable the NNG pubsub program

## Interface
- `[Kconfig:EXAMPLES_NNG_TEST]` - Build configuration option `EXAMPLES_NNG_TEST`
- `[Kconfig:EXAMPLES_NNG_TEST_STACKSIZE]` - Build configuration option `EXAMPLES_NNG_TEST_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `pubsub`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pubsub`
- `[pubsub.c:fatal]` - Public function `fatal()`
- `[pubsub.c:date]` - Public function `date()`
- `[pubsub.c:client_thread]` - Public function `client_thread()`
- `[pubsub.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[pubsub.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[pubsub.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
