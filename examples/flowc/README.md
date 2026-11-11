# flowc

## Overview
Serial flow control example (`flowc`). Enable the serial hardware flow control test.

## Interface
- `[Kconfig:EXAMPLES_FLOWC]` - Build configuration option `EXAMPLES_FLOWC`
- `[Kconfig:EXAMPLES_FLOWC_INPUT]` - Build configuration option `EXAMPLES_FLOWC_INPUT`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FLOWC_PROGNAME1)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FLOWC_PROGNAME2)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_FLOWC_PROGNAME1}`
- `[flowc.h:flowc_sender]` - Public function declaration `flowc_sender()`
- `[flowc.h:flowc_receiver]` - Public function declaration `flowc_receiver()`
- `[flowc_host.c:main]` - Application entry point `main()`
- `[flowc_mktestdata.c:main]` - Application entry point `main()`
- `[flowc_receiver.c:flowc_receiver]` - Public function `flowc_receiver()`
- `[flowc_sender.c:flowc_sender]` - Public function `flowc_sender()`
- `[flowc_target1.c:main]` - Application entry point `main()`
- `[flowc_target2.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SERIAL_TERMIOS]` - Requires kernel/app configuration `SERIAL_TERMIOS`
- `[flowc_host.c:CONFIG_EXAMPLES_FLOWC_SENDER1]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_SENDER1`
- `[flowc_receiver.c:CONFIG_EXAMPLES_FLOWC_INPUT]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_INPUT`
- `[flowc_receiver.c:CONFIG_EXAMPLES_FLOWC_RECEIVER_DELAY]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_RECEIVER_DELAY`
- `[flowc_receiver.c:CONFIG_SYSLOG_INTBUFFER]` - Configuration guard on `CONFIG_SYSLOG_INTBUFFER`
- `[flowc_receiver.c:argc]` - Validates command-line argument count `argc`
- `[flowc_sender.c:CONFIG_EXAMPLES_FLOWC_OUTPUT]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_OUTPUT`
- `[flowc_sender.c:argc]` - Validates command-line argument count `argc`
- `[flowc_target1.c:CONFIG_EXAMPLES_FLOWC_SENDER1]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_SENDER1`
- `[flowc_target2.c:CONFIG_EXAMPLES_FLOWC_SENDER1]` - Configuration guard on `CONFIG_EXAMPLES_FLOWC_SENDER1`

## Side Effects
- `[flowc_receiver.c:open]` - Opens device nodes or files via `open()`
- `[flowc_receiver.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[flowc_receiver.c:syslog]` - Writes diagnostic log entries via `syslog()`
- `[flowc_receiver.c:printf]` - Writes formatted output to standard output via `printf()`
- `[flowc_sender.c:open]` - Opens device nodes or files via `open()`
- `[flowc_sender.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[flowc_sender.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
