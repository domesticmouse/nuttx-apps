# fdpicxip

## Overview
FDPIC modules executed in place from xipfs demo (`fdpicxip`). Write FDPIC modules into xipfs at run time, the way a download would, then run them.  Their text is executed directly out of flash and shared between concurrent instances, while each instance gets its own data.

## Interface
- `[Kconfig:EXAMPLES_FDPICXIP]` - Build configuration option `EXAMPLES_FDPICXIP`
- `[Kconfig:EXAMPLES_FDPICXIP_MOUNTPT]` - Build configuration option `EXAMPLES_FDPICXIP_MOUNTPT`
- `[Makefile:PROGNAME]` - Registers application/module target `fdpicxip`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `fdpicxip`
- `[fdpicxip_main.c:main]` - Application entry point `main()`
- **modules**: [`./modules/README.md`](./modules/README.md) - NuttX `fdpicxip/modules` component implementing `mkblobs.sh`.

## Invariants
- `[Kconfig:depends on FS_XIPFS && FDPIC && LIBC_EXECFUNCS]` - Requires kernel/app configuration `FS_XIPFS && FDPIC && LIBC_EXECFUNCS`
- `[fdpicxip_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[fdpicxip_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[fdpicxip_main.c:open]` - Opens device nodes or files via `open()`
- `[fdpicxip_main.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[fdpicxip_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[fdpicxip_main.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
