# shv-nxboot-updater

## Overview
Silicon Heaven Firmware updates for NXBoot (`shv-nxboot-updater`). Enable the shv-nxboot-updater application.

## Interface
- `[Kconfig:EXAMPLES_SHV_NXBOOT_UPDATER]` - Build configuration option `EXAMPLES_SHV_NXBOOT_UPDATER`
- `[Kconfig:EXAMPLES_SHV_NXBOOT_UPDATER_PROGNAME]` - Build configuration option `EXAMPLES_SHV_NXBOOT_UPDATER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SHV_NXBOOT_UPDATER_PROGNAME)`
- `[shv_nxboot_updater.c:main]` - Application entry point `main()`
- `[shv_nxboot_updater.c:getopt]` - Command-line option parser supporting flags `"hm:i:p:t:u:"`
- **update-script**: [`./update-script/README.md`](./update-script/README.md) - NuttX `shv-nxboot-updater/update-script` component implementing `shvconfirm.py, shvflasher.py, tui.py`.

## Invariants
- `[Kconfig:depends on NETUTILS_LIBSHVC && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `NETUTILS_LIBSHVC && ENABLE_ALL_SIGNALS`

## Side Effects
- `[shv_nxboot_updater.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[shv_nxboot_updater.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
