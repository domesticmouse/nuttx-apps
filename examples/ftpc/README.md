# ftpc

## Overview
FTP client example (`ftpc`). Enable the FTP client example

## Interface
- `[Kconfig:EXAMPLES_FTPC]` - Build configuration option `EXAMPLES_FTPC`
- `[Kconfig:EXAMPLES_FTPC_STACKSIZE]` - Build configuration option `EXAMPLES_FTPC_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `ftpc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `ftpc`
- `[ftpc.h:int]` - Public function declaration `int()`
- `[ftpc.h:cmd_rlogin]` - Public function declaration `cmd_rlogin()`
- `[ftpc.h:cmd_rquit]` - Public function declaration `cmd_rquit()`
- `[ftpc.h:cmd_rchdir]` - Public function declaration `cmd_rchdir()`
- `[ftpc.h:cmd_rpwd]` - Public function declaration `cmd_rpwd()`
- `[ftpc.h:cmd_rcdup]` - Public function declaration `cmd_rcdup()`
- `[ftpc.h:cmd_rmkdir]` - Public function declaration `cmd_rmkdir()`
- `[ftpc.h:cmd_rrmdir]` - Public function declaration `cmd_rrmdir()`
- `[ftpc.h:cmd_runlink]` - Public function declaration `cmd_runlink()`
- `[ftpc.h:cmd_rchmod]` - Public function declaration `cmd_rchmod()`
- `[ftpc.h:cmd_rrename]` - Public function declaration `cmd_rrename()`
- `[ftpc.h:cmd_rsize]` - Public function declaration `cmd_rsize()`
- `[ftpc.h:cmd_rtime]` - Public function declaration `cmd_rtime()`
- `[ftpc.h:cmd_ridle]` - Public function declaration `cmd_ridle()`
- `[ftpc.h:cmd_rnoop]` - Public function declaration `cmd_rnoop()`
- `[ftpc.h:cmd_rhelp]` - Public function declaration `cmd_rhelp()`
- `[ftpc.h:cmd_rls]` - Public function declaration `cmd_rls()`
- `[ftpc.h:cmd_rget]` - Public function declaration `cmd_rget()`
- `[ftpc.h:cmd_rput]` - Public function declaration `cmd_rput()`
- `[ftpc_main.c:struct cmdmap_s]` - Structure definition `cmdmap_s`
- `[ftpc_main.c:ftpc_argument]` - Public function `ftpc_argument()`
- `[ftpc_main.c:ftpc_parse]` - Public function `ftpc_parse()`
- `[ftpc_main.c:main]` - Application entry point `main()`
- `[ftpc_main.c:getopt]` - Command-line option parser supporting flags `"46n"`
- `[ftpc_cmds.c:cmd_rlogin]` - Public function `cmd_rlogin()`
- `[ftpc_cmds.c:cmd_rquit]` - Public function `cmd_rquit()`
- `[ftpc_cmds.c:cmd_rchdir]` - Public function `cmd_rchdir()`
- `[ftpc_cmds.c:cmd_rpwd]` - Public function `cmd_rpwd()`
- `[ftpc_cmds.c:cmd_rcdup]` - Public function `cmd_rcdup()`
- `[ftpc_cmds.c:cmd_rmkdir]` - Public function `cmd_rmkdir()`
- `[ftpc_cmds.c:cmd_rrmdir]` - Public function `cmd_rrmdir()`

## Invariants
- `[ftpc.h:CONFIG_FTPC_LINELEN]` - Configuration guard on `CONFIG_FTPC_LINELEN`
- `[ftpc.h:CONFIG_FILE_STREAM]` - Configuration guard on `CONFIG_FILE_STREAM`
- `[ftpc_main.c:CONFIG_LIBC_NETDB]` - Configuration guard on `CONFIG_LIBC_NETDB`
- `[ftpc_main.c:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[ftpc_main.c:CONFIG_EXAMPLES_FTPC_FGETS]` - Configuration guard on `CONFIG_EXAMPLES_FTPC_FGETS`
- `[ftpc_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`
- `[ftpc_main.c:argc]` - Validates command-line argument count `argc`
- `[ftpc_cmds.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[ftpc_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[ftpc_cmds.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
