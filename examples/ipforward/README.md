# ipforward

## Overview
IP forwarding example (`ipforward`). Enable the IP forwarding example

## Interface
- `[Kconfig:EXAMPLES_IPFORWARD]` - Build configuration option `EXAMPLES_IPFORWARD`
- `[Kconfig:EXAMPLES_IPFORWARD_TCP]` - Build configuration option `EXAMPLES_IPFORWARD_TCP`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_IPFORWARD_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_IPFORWARD_PROGNAME}`
- `[ipforward.c:struct ipfwd_tun_s]` - Structure definition `ipfwd_tun_s`
- `[ipforward.c:struct ipfwd_state_s]` - Structure definition `ipfwd_state_s`
- `[ipforward.c:struct ipfwd_arg_s]` - Structure definition `ipfwd_arg_s`
- `[ipforward.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_TUN && (NET_TCP || NET_ICMPv6)]` - Requires kernel/app configuration `NET_TUN && (NET_TCP || NET_ICMPv6)`
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on NET_ICMPv6]` - Requires kernel/app configuration `NET_ICMPv6`
- `[ipforward.c:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[ipforward.c:CONFIG_NET_ETHERNET]` - Configuration guard on `CONFIG_NET_ETHERNET`
- `[ipforward.c:CONFIG_NET_6LOWPAN_EXTENDEDADDR]` - Configuration guard on `CONFIG_NET_6LOWPAN_EXTENDEDADDR`
- `[ipforward.c:CONFIG_EXAMPLES_IPFORWARD_TCP]` - Configuration guard on `CONFIG_EXAMPLES_IPFORWARD_TCP`

## Side Effects
- `[ipforward.c:/dev/tun]` - Opens or interacts with VFS/device path `/dev/tun`
- `[ipforward.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[ipforward.c:open]` - Opens device nodes or files via `open()`
- `[ipforward.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[ipforward.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ipforward.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[ipforward.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
