# `netutils/iptables`

## Overview
Provides iptables libary (`netutils/iptables`). iptable libary support.

## Interface
- [Kconfig:CONFIG_NETUTILS_IPTABLES]
- [xtables.c:xtables_insmod]
- [xtables.c:xtables_init_all]
- [xtables.c:xtables_parse_protocol]
- [xtables.c:xtables_option_tpcall]
- [xtables.c:xtables_option_mpcall]
- [xtables.c:xtables_option_tfcall]
- [xtables.c:xtables_option_mfcall]
- [xtables.c:xtables_options_xfrm]
- [xtables.c:xtables_merge_options]
- [xtables.c:xtables_find_match]
- [xtables.c:xtables_find_target]
- [xtables.c:xtables_compatible_revision]

## Invariants
- [Kconfig:CONFIG_NETUTILS_IPTABLES]: Build and feature compilation gated by `CONFIG_NETUTILS_IPTABLES`.

## Side Effects
- None

## Verification
- Run: `make test`
