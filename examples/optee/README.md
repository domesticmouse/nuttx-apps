# optee

## Overview
OP-TEE client example (`optee`). Enable the OP-TEE client example

## Interface
- `[Kconfig:EXAMPLES_OPTEE]` - Build configuration option `EXAMPLES_OPTEE`
- `[Kconfig:EXAMPLES_OPTEE_PROGNAME]` - Build configuration option `EXAMPLES_OPTEE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_OPTEE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_OPTEE_PROGNAME}`
- `[optee_main.c:struct tee_shm]` - Structure definition `tee_shm`
- `[optee_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[optee_main.c:/dev/tee0]` - Opens or interacts with VFS/device path `/dev/tee0`
- `[optee_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[optee_main.c:open]` - Opens device nodes or files via `open()`
- `[optee_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[optee_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
