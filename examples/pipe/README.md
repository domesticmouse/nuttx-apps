# pipe

## Overview
Pipe example (`pipe`). Enable the pipe example

## Interface
- `[Kconfig:EXAMPLES_PIPE]` - Build configuration option `EXAMPLES_PIPE`
- `[Kconfig:EXAMPLES_PIPE_STACKSIZE]` - Build configuration option `EXAMPLES_PIPE_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `pipe`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pipe`
- `[pipe.h:transfer_test]` - Public function declaration `transfer_test()`
- `[pipe.h:interlock_test]` - Public function declaration `interlock_test()`
- `[pipe.h:redirection_test]` - Public function declaration `redirection_test()`
- `[pipe_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PIPES]` - Requires kernel/app configuration `PIPES`
- `[pipe_main.c:CONFIG_DEV_FIFO_SIZE]` - Configuration guard on `CONFIG_DEV_FIFO_SIZE`
- `[pipe_main.c:CONFIG_DEV_PIPE_SIZE]` - Configuration guard on `CONFIG_DEV_PIPE_SIZE`

## Side Effects
- `[pipe.h:/var/testfifo-1]` - Opens or interacts with VFS/device path `/var/testfifo-1`
- `[pipe.h:/var/testfifo-2]` - Opens or interacts with VFS/device path `/var/testfifo-2`
- `[pipe_main.c:open]` - Opens device nodes or files via `open()`
- `[pipe_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`

## Verification
- Run: `make test`
