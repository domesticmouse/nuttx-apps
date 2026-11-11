# `include/netutils`

## Overview
Implements `include/netutils`: Start the discover daemon. Input Parameters:

## Interface
- [base64.h:base64_encode_length]
- [base64.h:base64_encode]
- [base64.h:base64_decode_length]
- [base64.h:base64_decode]
- [base64.h:base64w_encode]
- [base64.h:base64w_decode]
- [base64.h:base64url_encode]
- [base64.h:base64url_decode]
- [chat.h:struct chat_ctl]
- [chat.h:chat]
- [cmux.h:struct cmux_settings_s]
- [cmux.h:cmux_create]
- [curl4nx.h:enum curl4nxerrors_e]
- [curl4nx.h:enum curl4nxopt_e]
- [curl4nx.h:curl4nx_easy_strerror]
- [curl4nx.h:curl4nx_easy_init]
- [curl4nx.h:curl4nx_easy_escape]
- [curl4nx.h:curl4nx_easy_unescape]

## Invariants
- [base64.h:CONFIG_CODECS_BASE64]: Conditional compilation gated by `CONFIG_CODECS_BASE64`.
- [dhcpc.h:CONFIG_NETDB_DNSSERVER_NAMESERVERS]: Conditional compilation gated by `CONFIG_NETDB_DNSSERVER_NAMESERVERS`.
- [dhcpc.h:CONFIG_NETUTILS_DHCPC_NTP_SERVERS]: Conditional compilation gated by `CONFIG_NETUTILS_DHCPC_NTP_SERVERS`.
- [esp8266.h:CONFIG_NETUTILS_ESP8266]: Conditional compilation gated by `CONFIG_NETUTILS_ESP8266`.
- [ftpc.h:CONFIG_FTP_DEFTIMEO]: Conditional compilation gated by `CONFIG_FTP_DEFTIMEO`.
- [ftpc.h:CONFIG_FTP_ANONPWD]: Conditional compilation gated by `CONFIG_FTP_ANONPWD`.

## Side Effects
- [netlib.h:fopen]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
