# dhcpd

## Overview
DHCP server example (`dhcpd`). Enable the DHCP server example

## Interface
- `[Kconfig:EXAMPLES_DHCPD]` - Build configuration option `EXAMPLES_DHCPD`
- `[Kconfig:EXAMPLES_DHCPD_NOMAC]` - Build configuration option `EXAMPLES_DHCPD_NOMAC`
- `[Makefile:PROGNAME]` - Registers application/module target `dhcpd`
- `[Makefile:PROGNAME]` - Registers application/module target `dhcpd_start`
- `[Makefile:PROGNAME]` - Registers application/module target `dhcpd_stop`
- `[dhcpd_daemon.h:dhcpd_daemon]` - Public function declaration `dhcpd_daemon()`
- `[dhcpd_daemon.c:dhcpd_daemon]` - Public function `dhcpd_daemon()`
- `[dhcpd_start.c:main]` - Application entry point `main()`
- `[dhcpd_stop.c:main]` - Application entry point `main()`
- `[host.c:main]` - Application entry point `main()`
- `[target.c:main]` - Application entry point `main()`

## Invariants
- `[dhcpd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET
- `[dhcpd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET_UDP
- `[dhcpd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET_BROADCAST
- `[dhcpd_daemon.c:CONFIG_NET]` - Configuration guard on `CONFIG_NET`
- `[dhcpd_daemon.c:CONFIG_NET_UDP]` - Configuration guard on `CONFIG_NET_UDP`
- `[dhcpd_daemon.c:CONFIG_NET_BROADCAST]` - Configuration guard on `CONFIG_NET_BROADCAST`
- `[dhcpd_daemon.c:CONFIG_EXAMPLES_DHCPD_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_DHCPD_NOMAC`
- `[dhcpd_daemon.c:argc]` - Validates command-line argument count `argc`
- `[host.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- None

## Verification
- Run: `make test`
