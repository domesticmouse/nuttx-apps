# nxterm

## Overview
NxTerm example (`nxterm`). Enable the NxTerm example

## Interface
- `[Kconfig:EXAMPLES_NXTERM]` - Build configuration option `EXAMPLES_NXTERM`
- `[Kconfig:EXAMPLES_NXTERM_PROGNAME]` - Build configuration option `EXAMPLES_NXTERM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXTERM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXTERM_PROGNAME}`
- `[nxterm_internal.h:struct nxterm_state_s]` - Structure definition `nxterm_state_s`
- `[nxterm_internal.h:nxterm_listener]` - Public function declaration `nxterm_listener()`
- `[nxterm_internal.h:nxterm_pty_redirect]` - Public function declaration `nxterm_pty_redirect()`
- `[nxterm_main.c:main]` - Application entry point `main()`
- `[nxterm_listener.c:nxterm_listener]` - Public function `nxterm_listener()`
- `[nxterm_pty.c:struct nxterm_pty_s]` - Structure definition `nxterm_pty_s`
- `[nxterm_pty.c:nxterm_pty_redirect]` - Public function `nxterm_pty_redirect()`

## Invariants
- `[Kconfig:depends on NXTERM]` - Requires kernel/app configuration `NXTERM`
- `[Kconfig:depends on PSEUDOTERM && INPUT_KEYBOARD]` - Requires kernel/app configuration `PSEUDOTERM && INPUT_KEYBOARD`
- `[Kconfig:depends on !INPUT_KEYBOARD_BYTESTREAM]` - Requires kernel/app configuration `!INPUT_KEYBOARD_BYTESTREAM`
- `[nxterm_internal.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX=y)
- `[nxterm_internal.h:#error]` - Compile-time precondition: NxTerm is not enabled (CONFIG_NXTERM=y)
- `[nxterm_internal.h:#error]` - Compile-time precondition: Only CONFIG_NX_NPLANES==1 supported
- `[nxterm_internal.h:#error]` - Compile-time precondition: Invalid selection for CONFIG_EXAMPLES_NXTERM_BPP
- `[nxterm_internal.h:#error]` - Compile-time precondition: No pixel depth provided
- `[nxterm_internal.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nxterm_internal.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nxterm_internal.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nxterm_internal.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nxterm_internal.h:CONFIG_NXTERM]` - Configuration guard on `CONFIG_NXTERM`
- `[nxterm_internal.h:CONFIG_NSH_CONSOLE]` - Configuration guard on `CONFIG_NSH_CONSOLE`
- `[nxterm_internal.h:CONFIG_NX_NPLANES]` - Configuration guard on `CONFIG_NX_NPLANES`
- `[nxterm_main.c:CONFIG_NX_LCDDRIVER]` - Configuration guard on `CONFIG_NX_LCDDRIVER`
- `[nxterm_main.c:CONFIG_EXAMPLES_NXTERM_NSH_FALLBACK]` - Configuration guard on `CONFIG_EXAMPLES_NXTERM_NSH_FALLBACK`
- `[nxterm_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[nxterm_main.c:CONFIG_NSH_CONSOLE]` - Configuration guard on `CONFIG_NSH_CONSOLE`
- `[nxterm_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`

## Side Effects
- `[nxterm_internal.h:/dev/nxterm0]` - Opens or interacts with VFS/device path `/dev/nxterm0`
- `[nxterm_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxterm_main.c:open]` - Opens device nodes or files via `open()`
- `[nxterm_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxterm_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[nxterm_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxterm_listener.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxterm_pty.c:open]` - Opens device nodes or files via `open()`
- `[nxterm_pty.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[nxterm_pty.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nxterm_pty.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[nxterm_wndo.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxterm_wndo.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
