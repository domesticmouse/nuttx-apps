# `canutils/canlib`

## Overview
Provides CAN utility library (`canutils/canlib`). Enable the CAN utility library

## Interface
- [Kconfig:CONFIG_CANUTILS_CANLIB]
- [canlib_getbaud.c:canlib_getbaud]
- [canlib_getloopback.c:canlib_getloopback]
- [canlib_getsilent.c:canlib_getsilent]
- [canlib_setbaud.c:canlib_setbaud]
- [canlib_setloopback.c:canlib_setloopback]
- [canlib_setsilent.c:canlib_setsilent]

## Invariants
- [Kconfig:CONFIG_CANUTILS_CANLIB]: Build and feature compilation gated by `CONFIG_CANUTILS_CANLIB`.
- [Kconfig:depends on CAN]: Requires Kconfig dependency condition `CAN`.

## Side Effects
- [canlib_getbaud.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [canlib_getloopback.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [canlib_getsilent.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [canlib_setbaud.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [canlib_setloopback.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [canlib_setsilent.c:ioctl]: Issues device/driver control requests via `ioctl()`.

## Verification
- Run: `make test`
