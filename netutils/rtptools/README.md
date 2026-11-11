# `netutils/rtptools`

## Overview
Provides Enable RTP Tools (`netutils/rtptools`). RTP Tools is a set of small applications that can be used for processing RTP data.

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_RTPTOOLS_RTPPLAY_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_RTPTOOLS_RTPSEND_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_RTPTOOLS_RTPDUMP_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_RTPTOOLS_RTPTRANS_PROGNAME)]
- [Kconfig:CONFIG_NETUTILS_RTPTOOLS]
- [Kconfig:CONFIG_NETUTILS_RTPTOOLS_VERSION]
- [Kconfig:CONFIG_RTPTOOLS_APPS]
- [Kconfig:CONFIG_NETUTILS_RTPTOOLS_DEFAULT_TASK_STACKSIZE]
- [config.h:RTP_BIG_ENDIAN]
- [config.h:HAVE_MSGCONTROL]

## Invariants
- [Kconfig:CONFIG_NETUTILS_RTPTOOLS]: Build and feature compilation gated by `CONFIG_NETUTILS_RTPTOOLS`.
- [Kconfig:CONFIG_NETUTILS_RTPTOOLS_VERSION]: Build and feature compilation gated by `CONFIG_NETUTILS_RTPTOOLS_VERSION`.
- [config.h:CONFIG_ENDIAN_BIG]: Conditional compilation gated by `CONFIG_ENDIAN_BIG`.

## Side Effects
- None

## Verification
- Run: `make test`
