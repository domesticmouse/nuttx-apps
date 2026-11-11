# `industry/foc`

## Overview
Provides FOC Library (`industry/foc`). Enable or disable the FOC Library

## Interface
- [Kconfig:CONFIG_INDUSTRY_FOC]
- [Kconfig:CONFIG_INDUSTRY_FOC_DEBUG]
- [Kconfig:CONFIG_INDUSTRY_FOC_ERROR]
- [Kconfig:CONFIG_INDUSTRY_FOC_WARN]
- [foc_utils.c:foc_dev_stop]
- [foc_utils.c:foc_dev_start]
- [foc_utils.c:foc_dev_clearfault]
- [foc_utils.c:foc_dev_getstate]
- [foc_utils.c:foc_dev_setparams]
- [foc_utils.c:foc_dev_setcfg]
- [foc_utils.c:foc_dev_getinfo]
- [foc_utils.c:foc_cfg_print]
- `fixed16`: [./fixed16/README.md](./fixed16/README.md) - Implements `industry/foc/fixed16`: Initialize the open-loop FOC angle handler (fixed16) Input Parameter:
- `float`: [./float/README.md](./float/README.md) - Implements `industry/foc/float`: Initialize the open-loop FOC angle handler (float32) Input Parameter:

## Invariants
- [Kconfig:CONFIG_INDUSTRY_FOC]: Build and feature compilation gated by `CONFIG_INDUSTRY_FOC`.
- [Kconfig:CONFIG_INDUSTRY_FOC_DEBUG]: Build and feature compilation gated by `CONFIG_INDUSTRY_FOC_DEBUG`.
- [Kconfig:depends on MOTOR_FOC]: Requires Kconfig dependency condition `MOTOR_FOC`.
- [Kconfig:depends on MATH_CORDIC]: Requires Kconfig dependency condition `MATH_CORDIC`.
- [Kconfig:depends on SENSORS_QENCODER]: Requires Kconfig dependency condition `SENSORS_QENCODER`.

## Side Effects
- [foc_utils.c:ioctl]: Issues device/driver control requests via `ioctl()`.

## Verification
- Run: `make test`
