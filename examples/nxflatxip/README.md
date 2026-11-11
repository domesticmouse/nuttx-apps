# nxflatxip

## Overview
NXFLAT execute-in-place from xipfs demo (`nxflatxip`). Write an NXFLAT module into xipfs at run time, the way a download would, then run two instances of it concurrently.  The module's text is executed directly out of flash and shared between the instances, while each instance gets its own data.

## Interface
- `[Kconfig:EXAMPLES_NXFLATXIP]` - Build configuration option `EXAMPLES_NXFLATXIP`
- `[Kconfig:EXAMPLES_NXFLATXIP_MOUNTPT]` - Build configuration option `EXAMPLES_NXFLATXIP_MOUNTPT`
- `[Makefile:PROGNAME]` - Registers application/module target `nxflatxip`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nxflatxip`
- `[nxflatxip_main.c:xipmod_report]` - Public function `xipmod_report()`
- `[nxflatxip_main.c:main]` - Application entry point `main()`
- **module**: [`./module/README.md`](./module/README.md) - NuttX `nxflatxip/module` component: The module the demo downloads into xipfs and runs. Given a seed on the command line it fills an array derived from it, sleeps long enough for a second instance to do the same with a different seed, checks its own values are untouched, and hands the result to the firmware.  It reports the address of 

## Invariants
- `[Kconfig:depends on FS_XIPFS && NXFLAT && LIBC_EXECFUNCS]` - Requires kernel/app configuration `FS_XIPFS && NXFLAT && LIBC_EXECFUNCS`
- `[nxflatxip_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[nxflatxip_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[nxflatxip_main.c:open]` - Opens device nodes or files via `open()`
- `[nxflatxip_main.c:mount]` - Mounts filesystems via `mount()`
- `[nxflatxip_main.c:umount]` - Unmounts filesystems via `umount()`
- `[nxflatxip_main.c:exec]` - Executes binary programs in-place via `exec()`
- `[nxflatxip_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nxflatxip_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[nxflatxip_main.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
