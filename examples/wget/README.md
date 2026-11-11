# wget

## Overview
wget example (`wget`). Enable the wget example

## Interface
- `[Kconfig:EXAMPLES_WGET]` - Build configuration option `EXAMPLES_WGET`
- `[Kconfig:EXAMPLES_WGET_STACKSIZE]` - Build configuration option `EXAMPLES_WGET_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `wget`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `wget`
- `[wget_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on !NSH_NETINIT]` - Requires kernel/app configuration `!NSH_NETINIT`
- `[wget_main.c:#error]` - Compile-time precondition: You must define CONFIG_EXAMPLES_WGET_IPADDR
- `[wget_main.c:#error]` - Compile-time precondition: You must define CONFIG_EXAMPLES_WGET_DRIPADDR
- `[wget_main.c:#error]` - Compile-time precondition: You must define CONFIG_EXAMPLES_WGET_NETMASK
- `[wget_main.c:#error]` - Compile-time precondition: You must define CONFIG_NET
- `[wget_main.c:#error]` - Compile-time precondition: You must define CONFIG_NET_TCP
- `[wget_main.c:CONFIG_EXAMPLES_WGET_IPADDR]` - Configuration guard on `CONFIG_EXAMPLES_WGET_IPADDR`
- `[wget_main.c:CONFIG_EXAMPLES_WGET_DRIPADDR]` - Configuration guard on `CONFIG_EXAMPLES_WGET_DRIPADDR`
- `[wget_main.c:CONFIG_EXAMPLES_WGET_NETMASK]` - Configuration guard on `CONFIG_EXAMPLES_WGET_NETMASK`
- `[wget_main.c:CONFIG_NET]` - Configuration guard on `CONFIG_NET`
- `[wget_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[wget_main.c:open]` - Opens device nodes or files via `open()`
- `[wget_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[wget_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
