# `system/xrcedds/include/uxr/client`

## Overview
Implements `system/xrcedds/include/uxr/client` source and header components (`config.h`) in the NuttX application tree.

## Interface
- [config.h:UXR_CLIENT_VERSION_MAJOR]
- [config.h:UXR_CLIENT_VERSION_MINOR]
- [config.h:UXR_CLIENT_VERSION_MICRO]
- [config.h:UXR_CLIENT_VERSION_STR]
- [config.h:UCLIENT_PROFILE_UDP]
- [config.h:UCLIENT_PLATFORM_POSIX]
- [config.h:UCLIENT_TWEAK_XRCE_WRITE_LIMIT]
- [config.h:UCLIENT_PROFILE_STREAM_FRAMING]
- [config.h:UXR_CONFIG_MAX_OUTPUT_BEST_EFFORT_STREAMS]
- [config.h:UXR_CONFIG_MAX_OUTPUT_RELIABLE_STREAMS]
- [config.h:UXR_CONFIG_MAX_INPUT_BEST_EFFORT_STREAMS]
- [config.h:UXR_CONFIG_MAX_INPUT_RELIABLE_STREAMS]
- [config.h:UXR_CONFIG_MAX_SESSION_CONNECTION_ATTEMPTS]
- [config.h:UXR_CONFIG_MIN_SESSION_CONNECTION_INTERVAL]
- [config.h:UXR_CONFIG_MIN_HEARTBEAT_TIME_INTERVAL]
- [config.h:UXR_CONFIG_UDP_TRANSPORT_MTU]

## Invariants
- [config.h:CONFIG_SYSTEM_XRCEDDS_STREAM_FRAMING]: Conditional compilation gated by `CONFIG_SYSTEM_XRCEDDS_STREAM_FRAMING`.

## Side Effects
- None

## Verification
- Run: `make test`
