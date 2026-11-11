# netloop

## Overview
Local loopback example (`netloop`). Enable the local loopback example

## Interface
- `[Kconfig:EXAMPLES_NETLOOP]` - Build configuration option `EXAMPLES_NETLOOP`
- `[Kconfig:EXAMPLES_NETLOOP_KEEPALIVE]` - Build configuration option `EXAMPLES_NETLOOP_KEEPALIVE`
- `[Makefile:PROGNAME]` - Registers application/module target `netloop`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `netloop`
- `[netloop.h:lo_listener]` - Public function declaration `lo_listener()`
- `[lo_main.c:main]` - Application entry point `main()`
- `[lo_listener.c:struct net_listener_s]` - Structure definition `net_listener_s`
- `[lo_listener.c:lo_listener]` - Public function `lo_listener()`

## Invariants
- `[Kconfig:depends on NET_LOOPBACK && NET_TCP && NET_TCPBACKLOG && NET_TCP_WRITE_BUFFERS && NET_IPv4]` - Requires kernel/app configuration `NET_LOOPBACK && NET_TCP && NET_TCPBACKLOG && NET_TCP_WRITE_BUFFERS && NET_IPv4`
- `[Kconfig:depends on NET_TCP_KEEPALIVE]` - Requires kernel/app configuration `NET_TCP_KEEPALIVE`
- `[netloop.h:#error]` - Compile-time precondition: Network socket support not enabled
- `[netloop.h:#error]` - Compile-time precondition: TCP not configured correctly
- `[netloop.h:#error]` - Compile-time precondition: This test only works with IPv4
- `[netloop.h:CONFIG_NET]` - Configuration guard on `CONFIG_NET`
- `[netloop.h:CONFIG_NET_TCP]` - Configuration guard on `CONFIG_NET_TCP`
- `[netloop.h:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[lo_main.c:CONFIG_EXAMPLES_NETLOOP_KEEPALIVE]` - Configuration guard on `CONFIG_EXAMPLES_NETLOOP_KEEPALIVE`

## Side Effects
- `[lo_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[lo_main.c:connect]` - Connects sockets to remote peers via `connect()`
- `[lo_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[lo_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[lo_listener.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[lo_listener.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[lo_listener.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[lo_listener.c:listen]` - Places sockets into passive listening state via `listen()`
- `[lo_listener.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
