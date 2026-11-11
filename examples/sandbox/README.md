# sandbox

## Overview
Protected-build sandbox containment test (`sandbox`). A test that deliberately tries to escape the kernel/user boundary of a protected or kernel build, and checks that the attempt is contained: the offending process is terminated and everything else keeps running.

## Interface
- `[Kconfig:EXAMPLES_SANDBOX]` - Build configuration option `EXAMPLES_SANDBOX`
- `[Kconfig:EXAMPLES_SANDBOX_PROGNAME]` - Build configuration option `EXAMPLES_SANDBOX_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SANDBOX_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SANDBOX_PROGNAME}`
- `[sandbox_main.c:struct sandbox_target_s]` - Structure definition `sandbox_target_s`
- `[sandbox_main.c:enum sandbox_expect_e]` - Enumeration `sandbox_expect_e`
- `[sandbox_main.c:main]` - Application entry point `main()`

## Invariants
- `[sandbox_main.c:CONFIG_NUTTX_USERSPACE]` - Configuration guard on `CONFIG_NUTTX_USERSPACE`
- `[sandbox_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[sandbox_main.c:/proc/%d/group/fd]` - Opens or interacts with VFS/device path `/proc/%d/group/fd`
- `[sandbox_main.c:/proc/meminfo]` - Opens or interacts with VFS/device path `/proc/meminfo`
- `[sandbox_main.c:open]` - Opens device nodes or files via `open()`
- `[sandbox_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[sandbox_main.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[sandbox_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[sandbox_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
