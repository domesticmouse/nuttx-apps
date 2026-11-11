# `netutils/plcatool`

## Overview
Provides plcatool support (`netutils/plcatool`). Build in support for the plcatool command. This command allows configuring the PLCA access method in 10BASE-T1S network adapters supporting PLCA.

## Interface
- [Makefile:PROGNAME=plcatool]
- [Kconfig:CONFIG_NETUTILS_PLCATOOL]
- [oa_tc14.h:OA_TC14_PLCA_MMD]
- [oa_tc14.h:OA_TC14_IDVER_ADDR]
- [oa_tc14.h:OA_TC14_IDVER_IDM_MASK]
- [oa_tc14.h:OA_TC14_IDVER_IDM_POS]
- [oa_tc14.h:OA_TC14_IDVER_VER_MASK]
- [oa_tc14.h:OA_TC14_IDVER_VER_POS]
- [oa_tc14.h:OA_TC14_IDVER_VAL]
- [oa_tc14.h:OA_TC14_CTRL0_ADDR]
- [oa_tc14.h:OA_TC14_CTRL0_EN_MASK]
- [oa_tc14.h:OA_TC14_CTRL0_EN_POS]
- [oa_tc14.h:OA_TC14_CTRL0_RST_MASK]
- [oa_tc14.h:OA_TC14_CTRL0_RST_POS]
- [oa_tc14.h:OA_TC14_CTRL1_ADDR]
- [oa_tc14.h:OA_TC14_CTRL1_NCNT_MASK]
- [plcatool.c:enum plcatool_cmd_e]
- [plcatool.c:struct plcatool_cfg_s]

## Invariants
- [Kconfig:CONFIG_NETUTILS_PLCATOOL]: Build and feature compilation gated by `CONFIG_NETUTILS_PLCATOOL`.

## Side Effects
- [plcatool.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [plcatool.c:close]: Performs VFS file or device descriptor I/O operations.
- [plcatool.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [plcatool.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
