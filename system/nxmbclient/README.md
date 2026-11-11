# `system/nxmbclient`

## Overview
Provides NxModbus Client Tool (`system/nxmbclient`). Enable the NxModbus client command-line tool. This utility allows you to perform Modbus client operations from the command line,

## Interface
- [Makefile:PROGNAME=$(CONFIG_NXMBCLIENT_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NXMBCLIENT]
- [Kconfig:CONFIG_NXMBCLIENT_PROGNAME]
- [Kconfig:CONFIG_NXMBCLIENT_PRIORITY]
- [Kconfig:CONFIG_NXMBCLIENT_STACKSIZE]
- [nxmbclient_main.c:enum transport_type_e]
- [nxmbclient_main.c:struct nxmbclient_config_s]
- [nxmbclient_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXMBCLIENT]: Build and feature compilation gated by `CONFIG_SYSTEM_NXMBCLIENT`.
- [Kconfig:CONFIG_NXMBCLIENT_PROGNAME]: Build and feature compilation gated by `CONFIG_NXMBCLIENT_PROGNAME`.
- [Kconfig:depends on NXMODBUS_CLIENT]: Requires Kconfig dependency condition `NXMODBUS_CLIENT`.

## Side Effects
- [nxmbclient_main.c:malloc]: Allocates or releases dynamic heap memory.
- [nxmbclient_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
