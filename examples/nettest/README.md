# nettest

## Overview
Network test example (`nettest`). Enable the network test example

## Interface
- `[Kconfig:EXAMPLES_NETTEST]` - Build configuration option `EXAMPLES_NETTEST`
- `[Kconfig:EXAMPLES_NETTEST_SENDSIZE]` - Build configuration option `EXAMPLES_NETTEST_SENDSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NETTEST_PROGNAME1)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NETTEST_PROGNAME2)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NETTEST_PROGNAME1}`
- `[nettest.h:nettest_initialize]` - Public function declaration `nettest_initialize()`
- `[nettest.h:nettest_cmdline]` - Public function declaration `nettest_cmdline()`
- `[nettest.h:nettest_client]` - Public function declaration `nettest_client()`
- `[nettest.h:nettest_server]` - Public function declaration `nettest_server()`
- `[nettest_client.c:nettest_client]` - Public function `nettest_client()`
- `[nettest_cmdline.c:nettest_cmdline]` - Public function `nettest_cmdline()`
- `[nettest_host.c:main]` - Application entry point `main()`
- `[nettest_netinit.c:nettest_initialize]` - Public function `nettest_initialize()`
- `[nettest_server.c:nettest_server]` - Public function `nettest_server()`
- `[nettest_target1.c:main]` - Application entry point `main()`
- `[nettest_target2.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on NET_SOCKOPTS]` - Requires kernel/app configuration `NET_SOCKOPTS`
- `[Kconfig:depends on NET_LOOPBACK || IEEE802154_LOOPBACK || PKTRADIO_LOOPBACK]` - Requires kernel/app configuration `NET_LOOPBACK || IEEE802154_LOOPBACK || PKTRADIO_LOOPBACK`
- `[nettest.h:CONFIG_NET_SOLINGER]` - Configuration guard on `CONFIG_NET_SOLINGER`
- `[nettest.h:CONFIG_EXAMPLES_NETTEST_IP]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_IP`
- `[nettest.h:CONFIG_EXAMPLES_NETTEST_SERVER_PORTNO]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_SERVER_PORTNO`
- `[nettest.h:CONFIG_EXAMPLES_NETTEST_SENDSIZE]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_SENDSIZE`
- `[nettest_client.c:CONFIG_EXAMPLES_NETTEST_IP]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_IP`
- `[nettest_client.c:CONFIG_EXAMPLES_NETTEST_PERFORMANCE]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_PERFORMANCE`
- `[nettest_cmdline.c:CONFIG_EXAMPLES_NETTEST_IP]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_IP`
- `[nettest_cmdline.c:CONFIG_EXAMPLES_NETTEST_LOOPBACK]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_LOOPBACK`
- `[nettest_cmdline.c:argc]` - Validates command-line argument count `argc`
- `[nettest_host.c:CONFIG_EXAMPLES_NETTEST_SERVER]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_SERVER`
- `[nettest_netinit.c:CONFIG_EXAMPLES_NETTEST_INIT]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_INIT`
- `[nettest_netinit.c:CONFIG_EXAMPLES_NETTEST_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_DEVNAME`
- `[nettest_netinit.c:CONFIG_EXAMPLES_NETTEST_IP]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_IP`
- `[nettest_netinit.c:CONFIG_EXAMPLES_NETTEST_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_NOMAC`
- `[nettest_server.c:CONFIG_EXAMPLES_NETTEST_IP]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_IP`
- `[nettest_server.c:CONFIG_EXAMPLES_NETTEST_PERFORMANCE]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_PERFORMANCE`
- `[nettest_server.c:CONFIG_EXAMPLES_NETTEST_LOOPBACK]` - Configuration guard on `CONFIG_EXAMPLES_NETTEST_LOOPBACK`

## Side Effects
- `[nettest_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[nettest_client.c:connect]` - Connects sockets to remote peers via `connect()`
- `[nettest_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nettest_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[nettest_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[nettest_server.c:listen]` - Places sockets into passive listening state via `listen()`
- `[nettest_server.c:accept]` - Accepts incoming socket connections via `accept()`
- `[nettest_server.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nettest_target1.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[nettest_target1.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
