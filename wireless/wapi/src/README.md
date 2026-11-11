# `wireless/wapi/src`

## Overview
Implements `wireless/wapi/src`: Input Parameters: sockfd - Opened network socket

## Interface
- [util.h:wapi_ioctl_command_name]
- [util.h:WAPI_IOCTL_STRERROR]
- [util.h:WAPI_STRERROR]
- [util.h:WAPI_ERROR]
- [util.h:WAPI_VALIDATE_PTR]
- [driver_wext.c:wpa_driver_wext_get_key_ext]
- [driver_wext.c:wpa_driver_wext_set_key_ext]
- [driver_wext.c:wpa_driver_wext_associate]
- [driver_wext.c:wpa_driver_wext_set_auth_param]
- [driver_wext.c:wpa_driver_wext_get_auth_param]
- [driver_wext.c:wpa_driver_wext_disconnect]
- [network.c:wapi_get_ifup]
- [network.c:wapi_set_ifup]
- [network.c:wapi_set_ifdown]
- [network.c:wapi_get_ip]
- [network.c:wapi_set_ip]
- [network.c:wapi_get_netmask]
- [network.c:wapi_set_netmask]

## Invariants
- [util.h:CONFIG_LIBC_STRERROR]: Conditional compilation gated by `CONFIG_LIBC_STRERROR`.
- [driver_wext.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ifname != NULL && key != NULL && key_len > 0)` precondition.
- [driver_wext.c:DEBUGASSERT]: Enforces `DEBUGASSERT(wconfig != NULL)` precondition.
- [driver_wext.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ifname != NULL)` precondition.
- [network.c:CONFIG_NET_ROUTE]: Conditional compilation gated by `CONFIG_NET_ROUTE`.
- [util.c:CONFIG_WIRELESS_WAPI_INITCONF]: Conditional compilation gated by `CONFIG_WIRELESS_WAPI_INITCONF`.

## Side Effects
- [util.h:ioctl]: Issues device/driver control requests via `ioctl()`.
- [driver_wext.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [driver_wext.c:close]: Performs VFS file or device descriptor I/O operations.
- [driver_wext.c:malloc]: Allocates or releases dynamic heap memory.
- [network.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [util.c:open]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
