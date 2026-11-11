# tcpblaster

## Overview
TCP Performance Test (`tcpblaster`). Enable the network test example

## Interface
- `[Kconfig:EXAMPLES_TCPBLASTER]` - Build configuration option `EXAMPLES_TCPBLASTER`
- `[Kconfig:EXAMPLES_TCPBLASTER_SENDSIZE]` - Build configuration option `EXAMPLES_TCPBLASTER_SENDSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TCPBLASTER_PROGNAME1)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TCPBLASTER_PROGNAME2)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TCPBLASTER_PROGNAME1}`
- `[tcpblaster.h:tcpblaster_initialize]` - Public function declaration `tcpblaster_initialize()`
- `[tcpblaster.h:tcpblaster_cmdline]` - Public function declaration `tcpblaster_cmdline()`
- `[tcpblaster.h:tcpblaster_client]` - Public function declaration `tcpblaster_client()`
- `[tcpblaster.h:tcpblaster_server]` - Public function declaration `tcpblaster_server()`
- `[tcpblaster_client.c:tcpblaster_client]` - Public function `tcpblaster_client()`
- `[tcpblaster_cmdline.c:tcpblaster_cmdline]` - Public function `tcpblaster_cmdline()`
- `[tcpblaster_host.c:main]` - Application entry point `main()`
- `[tcpblaster_netinit.c:tcpblaster_initialize]` - Public function `tcpblaster_initialize()`
- `[tcpblaster_server.c:tcpblaster_server]` - Public function `tcpblaster_server()`
- `[tcpblaster_target1.c:main]` - Application entry point `main()`
- `[tcpblaster_target2.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on NET_LOOPBACK || IEEE802154_LOOPBACK || PKTRADIO_LOOPBACK]` - Requires kernel/app configuration `NET_LOOPBACK || IEEE802154_LOOPBACK || PKTRADIO_LOOPBACK`
- `[Kconfig:depends on !EXAMPLES_TCPBLASTER_LOOPBACK]` - Requires kernel/app configuration `!EXAMPLES_TCPBLASTER_LOOPBACK`
- `[tcpblaster.h:CONFIG_NET_SOLINGER]` - Configuration guard on `CONFIG_NET_SOLINGER`
- `[tcpblaster.h:CONFIG_EXAMPLES_TCPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_IP`
- `[tcpblaster.h:CONFIG_EXAMPLES_TCPBLASTER_SERVER_PORTNO]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_SERVER_PORTNO`
- `[tcpblaster.h:CONFIG_EXAMPLES_TCPBLASTER_SENDSIZE]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_SENDSIZE`
- `[tcpblaster_client.c:CONFIG_EXAMPLES_TCPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_IP`
- `[tcpblaster_client.c:CONFIG_EXAMPLES_TCPBLASTER_POLLOUT]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_POLLOUT`
- `[tcpblaster_cmdline.c:CONFIG_EXAMPLES_TCPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_IP`
- `[tcpblaster_cmdline.c:CONFIG_EXAMPLES_TCPBLASTER_LOOPBACK]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_LOOPBACK`
- `[tcpblaster_cmdline.c:argc]` - Validates command-line argument count `argc`
- `[tcpblaster_host.c:CONFIG_EXAMPLES_TCPBLASTER_SERVER]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_SERVER`
- `[tcpblaster_netinit.c:CONFIG_EXAMPLES_TCPBLASTER_INIT]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_INIT`
- `[tcpblaster_netinit.c:CONFIG_EXAMPLES_TCPBLASTER_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_DEVNAME`
- `[tcpblaster_netinit.c:CONFIG_EXAMPLES_TCPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_IP`
- `[tcpblaster_netinit.c:CONFIG_EXAMPLES_TCPBLASTER_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_NOMAC`
- `[tcpblaster_server.c:CONFIG_EXAMPLES_TCPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_IP`
- `[tcpblaster_server.c:CONFIG_EXAMPLES_TCPBLASTER_LOOPBACK]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_LOOPBACK`
- `[tcpblaster_server.c:CONFIG_EXAMPLES_TCPBLASTER_POLLIN]` - Configuration guard on `CONFIG_EXAMPLES_TCPBLASTER_POLLIN`

## Side Effects
- `[tcpblaster_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[tcpblaster_client.c:connect]` - Connects sockets to remote peers via `connect()`
- `[tcpblaster_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[tcpblaster_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[tcpblaster_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[tcpblaster_server.c:listen]` - Places sockets into passive listening state via `listen()`
- `[tcpblaster_server.c:accept]` - Accepts incoming socket connections via `accept()`
- `[tcpblaster_server.c:printf]` - Writes formatted output to standard output via `printf()`
- `[tcpblaster_target1.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[tcpblaster_target1.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
