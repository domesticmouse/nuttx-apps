# `system/uorb`

## Overview
Implements uorb(micro object request broker) (`system/uorb`) for the NuttX application subsystem.

## Interface
- [Makefile:PROGNAME=uorb_listener]
- [Makefile:PROGNAME=uorb_generator]
- [Makefile:PROGNAME=uorb_unit_test]
- [Kconfig:CONFIG_UORB]
- [Kconfig:CONFIG_UORB_PRIORITY]
- [Kconfig:CONFIG_UORB_STACKSIZE]
- [Kconfig:CONFIG_UORB_FORMAT]
- [generator.c:struct sensor_gen_info_s]
- [generator.c:main]
- [listener.c:struct listen_object_s]
- [listener.c:main]
- `sensor`: [./sensor/README.md](./sensor/README.md) - Implements `system/uorb/sensor` source and header components (`accel.c`, `accel.h`, `angle.c`, `angle.h` and 93 more files) in the NuttX application tree.
- `test`: [./test/README.md](./test/README.md) - Implements `system/uorb/test` source and header components (`utility.c`, `utility.h`) in the NuttX application tree.
- `uORB`: [./uORB/README.md](./uORB/README.md) - Implements `system/uorb/uORB`: Open device node as advertiser / subscriber, register node and save meta in driver for first user, set buffer number for advertisers.

## Invariants
- [Kconfig:CONFIG_UORB]: Build and feature compilation gated by `CONFIG_UORB`.
- [Kconfig:CONFIG_UORB_PRIORITY]: Build and feature compilation gated by `CONFIG_UORB_PRIORITY`.
- [Kconfig:depends on SENSORS && USENSOR]: Requires Kconfig dependency condition `SENSORS && USENSOR`.
- [Kconfig:depends on EVENT_FD]: Requires Kconfig dependency condition `EVENT_FD`.
- [Kconfig:depends on LIBC_FLOATINGPOINT && SENSORS_USE_FLOAT]: Requires Kconfig dependency condition `LIBC_FLOATINGPOINT && SENSORS_USE_FLOAT`.
- [listener.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.

## Side Effects
- [generator.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [generator.c:zalloc]: Allocates or releases dynamic heap memory.
- [listener.c:mkdir]: Performs VFS file or device descriptor I/O operations.
- [listener.c:malloc]: Allocates or releases dynamic heap memory.
- [listener.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
