# Wireless / `wapi` WAPI

## Overview

```
`_`_`_`_____`_____`__`
|`|`|`|``_``|``_``|``|
|`|`|`|`````|```__|``|
|_____|__|__|__|``|__|
```

WAPI (Wireless API) provides an easy-to-use function set to configure wireless
network interfaces on a GNU/Linux system. One can think WAPI as a lightweight C
API for `iwconfig`, `wlanconfig`, `ifconfig`, and `route` commands. (But it is
not a thin wrapper for these command line tools.) It is designed to be used in
wireless heteregenous network research projects and supported by BWRC (Berkeley
Wireless Research Center) and WISERLAB (Wireless Information Systems Engineering
Research Laboratory at Özyeğin University).

For source codes, see http://github.com/vy/wapi. The most recent version of the
documentation is (hopefully) always available at http://vy.github.com/wapi.

## Subdirectories & Boundaries
- `src`: [./src/README.md](./src/README.md) - Implementation of the `wapi` CLI command tool, network/wireless `ioctl` wrappers, WEXT driver helpers, and JSON configuration persistence.

## Interface
- `[Kconfig:WIRELESS_WAPI]`, `[Kconfig:WIRELESS_WAPI_CMDTOOL]`, `[Kconfig:WIRELESS_WAPI_INITCONF]`: Kconfig options enabling the WAPI library, CLI tool (`wapi`), and JSON configuration file support.
- `[src/wapi.c:main]`: Command-line interface entry point (`wapi`).
- `[src/network.c:wapi_get_ifup]` / `[src/network.c:wapi_set_ifup]` / `[src/network.c:wapi_set_ifdown]` / `[src/network.c:wapi_get_ip]` / `[src/network.c:wapi_set_ip]` / `[src/network.c:wapi_add_route_gw]`: Network interface state, IPv4 address/netmask, and gateway route helpers.
- `[src/wireless.c:wapi_get_essid]` / `[src/wireless.c:wapi_set_essid]` / `[src/wireless.c:wapi_get_freq]` / `[src/wireless.c:wapi_set_freq]` / `[src/wireless.c:wapi_scan_init]` / `[src/wireless.c:wapi_scan_coll]`: Wireless SSID, channel/frequency, bitrate, TX power, and access-point scan APIs.
- `[src/driver_wext.c:wpa_driver_wext_associate]` / `[src/driver_wext.c:wpa_driver_wext_set_key_ext]` / `[src/driver_wext.c:wpa_driver_wext_disconnect]`: Wireless Extensions (WEXT) association and WPA key configuration APIs.

## Invariants
- `[Kconfig:WIRELESS_WAPI]`: Depends on `NET && DRIVERS_WIRELESS`; `[Kconfig:WIRELESS_WAPI_INITCONF]` depends on `NETUTILS_CJSON`.
- `[src/util.h:WAPI_VALIDATE_PTR]`: Returns `-EINVAL` if any validated pointer parameter is `NULL`.
- `[src/wapi.c:wapi_psk_cmd]`: Requires WPA passphrase length to be between 8 and 63 characters inclusive, returning `-EINVAL` otherwise.

## Side Effects
- `[src/util.c:wapi_make_socket]`, `[src/network.c:wapi_set_ifup]`, and `[src/wireless.c:wapi_scan_coll]`: Open control sockets via `socket()`, issue `SIOC*` and `SIOCSIW*`/`SIOCGIW*` network/wireless `ioctl` calls, and allocate scan result lists on the heap.
- `[src/util.c:wapi_load_config]` and `[src/util.c:wapi_save_config]`: Read and write JSON wireless configuration files on the filesystem.

## Verification
- Run: `make test`

## License

Copyright (c) 2010, Volkan YAZICI <volkan.yazici@gmail.com> All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

- Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.
- Redistributions in binary form must reproduce the above copyright notice, this
  list of conditions and the following disclaimer in the documentation and/or
  other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
