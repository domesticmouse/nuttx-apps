# rfid_readuid

## Overview
RFID Read UID example (`rfid_readuid`). Enable the RFID READUID example

## Interface
- `[Kconfig:EXAMPLES_RFID_READUID]` - Build configuration option `EXAMPLES_RFID_READUID`
- `[Kconfig:EXAMPLES_RFID_READUID_PROGNAME]` - Build configuration option `EXAMPLES_RFID_READUID_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_RFID_READUID_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_RFID_READUID_PROGNAME}`
- `[rfid_readuid.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on CL_MFRC522]` - Requires kernel/app configuration `CL_MFRC522`
- `[rfid_readuid.c:CONFIG_EXAMPLES_RFID_READUID_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_RFID_READUID_DEVNAME`

## Side Effects
- `[rfid_readuid.c:/dev/rfid0]` - Opens or interacts with VFS/device path `/dev/rfid0`
- `[rfid_readuid.c:open]` - Opens device nodes or files via `open()`
- `[rfid_readuid.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[rfid_readuid.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
