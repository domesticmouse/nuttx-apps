# `include/nshlib`

## Overview
Implements `include/nshlib`: This interface is used to initialize the NuttShell (NSH).

## Interface
- [nshlib.h:struct nsh_param_s]
- [nshlib.h:nsh_initialize]
- [nshlib.h:nsh_consolemain]
- [nshlib.h:nsh_telnetmain]
- [nshlib.h:nsh_telnetstart]
- [nshlib.h:platform_motd]
- [nshlib.h:platform_skip_login]
- [nshlib.h:platform_challenge]
- [nshlib.h:platform_user_verify]
- [nshlib.h:nsh_system]
- [nshlib.h:nsh_system_ctty]
- [nshlib.h:HAVE_USB_CONSOLE]
- [nshlib.h:SCHED_NSH]

## Invariants
- [nshlib.h:CONFIG_USBDEV]: Conditional compilation gated by `CONFIG_USBDEV`.
- [nshlib.h:CONFIG_PL2303]: Conditional compilation gated by `CONFIG_PL2303`.
- [nshlib.h:CONFIG_PL2303_CONSOLE]: Conditional compilation gated by `CONFIG_PL2303_CONSOLE`.
- [nshlib.h:CONFIG_RR_INTERVAL]: Conditional compilation gated by `CONFIG_RR_INTERVAL`.
- [nshlib.h:CONFIG_NSH_PLATFORM_MOTD]: Conditional compilation gated by `CONFIG_NSH_PLATFORM_MOTD`.
- [nshlib.h:CONFIG_NSH_PLATFORM_SKIP_LOGIN]: Conditional compilation gated by `CONFIG_NSH_PLATFORM_SKIP_LOGIN`.

## Side Effects
- None

## Verification
- Run: `make test`
