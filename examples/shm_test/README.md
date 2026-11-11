# shm_test

## Overview
SHM example (`shm_test`). Enable the SHM example which has an shm producer and consumer

## Interface
- `[Kconfig:EXAMPLES_SHM]` - Build configuration option `EXAMPLES_SHM`
- `[Kconfig:EXAMPLES_SHM_PROGNAME]` - Build configuration option `EXAMPLES_SHM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SHM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SHM_PROGNAME}`
- `[shm_main.c:shm_producer]` - Public function `shm_producer()`
- `[shm_main.c:shm_consumer]` - Public function `shm_consumer()`
- `[shm_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FS_SHMFS]` - Requires kernel/app configuration `FS_SHMFS`

## Side Effects
- `[shm_main.c:shm_open]` - Opens POSIX shared memory objects via `shm_open()`
- `[shm_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[shm_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
