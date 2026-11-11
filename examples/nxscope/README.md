# nxscope

## Overview
nxscope example (`nxscope`). Enable the nxscope example

## Interface
- `[Kconfig:EXAMPLES_NXSCOPE]` - Build configuration option `EXAMPLES_NXSCOPE`
- `[Kconfig:EXAMPLES_NXSCOPE_PROGNAME]` - Build configuration option `EXAMPLES_NXSCOPE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXSCOPE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXSCOPE_PROGNAME}`
- `[nxscope_main.c:struct nxscope_thr_env_s]` - Structure definition `nxscope_thr_env_s`
- `[nxscope_main.c:main]` - Application entry point `main()`
- `[nxscope_main.c:getopt]` - Command-line option parser supporting flags `"i:m:"`

## Invariants
- `[Kconfig:depends on LOGGING_NXSCOPE]` - Requires kernel/app configuration `LOGGING_NXSCOPE`
- `[Kconfig:depends on CDCACM]` - Requires kernel/app configuration `CDCACM`
- `[Kconfig:depends on LOGGING_NXSCOPE_CRICHANNELS]` - Requires kernel/app configuration `LOGGING_NXSCOPE_CRICHANNELS`
- `[nxscope_main.c:#error]` - Compile-time precondition: math library must be selected for this example
- `[nxscope_main.c:CONFIG_EXAMPLES_NXSCOPE_TIMER]` - Configuration guard on `CONFIG_EXAMPLES_NXSCOPE_TIMER`
- `[nxscope_main.c:CONFIG_LIBM_NONE]` - Configuration guard on `CONFIG_LIBM_NONE`
- `[nxscope_main.c:CONFIG_EXAMPLES_NXSCOPE_CHARLOG]` - Configuration guard on `CONFIG_EXAMPLES_NXSCOPE_CHARLOG`
- `[nxscope_main.c:CONFIG_LOGGING_NXSCOPE_CRICHANNELS]` - Configuration guard on `CONFIG_LOGGING_NXSCOPE_CRICHANNELS`
- `[nxscope_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`

## Side Effects
- `[nxscope_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxscope_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[nxscope_main.c:open]` - Opens device nodes or files via `open()`
- `[nxscope_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxscope_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[nxscope_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
