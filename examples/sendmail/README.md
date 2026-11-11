# sendmail

## Overview
Sendmail example (`sendmail`). Enable the sendmail example

## Interface
- `[Kconfig:EXAMPLES_SENDMAIL]` - Build configuration option `EXAMPLES_SENDMAIL`
- `[Kconfig:EXAMPLES_SENDMAIL_NOMAC]` - Build configuration option `EXAMPLES_SENDMAIL_NOMAC`
- `[Makefile:PROGNAME]` - Registers application/module target `sendmail`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `sendmail`
- `[sendmail_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_IPv4]` - Requires kernel/app configuration `NET_IPv4`
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_RECIPIENT
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_IPADDR
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_DRIPADDR
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_SERVERADDR
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_PORT
- `[sendmail_main.c:#error]` - Compile-time precondition: You must provide CONFIG_EXAMPLES_SENDMAIL_NETMASK
- `[sendmail_main.c:CONFIG_EXAMPLES_SENDMAIL_RECIPIENT]` - Configuration guard on `CONFIG_EXAMPLES_SENDMAIL_RECIPIENT`
- `[sendmail_main.c:CONFIG_EXAMPLES_SENDMAIL_IPADDR]` - Configuration guard on `CONFIG_EXAMPLES_SENDMAIL_IPADDR`
- `[sendmail_main.c:CONFIG_EXAMPLES_SENDMAIL_DRIPADDR]` - Configuration guard on `CONFIG_EXAMPLES_SENDMAIL_DRIPADDR`
- `[sendmail_main.c:CONFIG_EXAMPLES_SENDMAIL_SERVERADDR]` - Configuration guard on `CONFIG_EXAMPLES_SENDMAIL_SERVERADDR`

## Side Effects
- `[sendmail_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
