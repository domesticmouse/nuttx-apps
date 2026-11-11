# `system/curl`

## Overview
Provides curl HTTP command (`system/curl`). Enable the "curl" command: a small command-line HTTP client supporting GET and POST (and other methods via -X), custom

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_CURL_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_CURL]
- [Kconfig:CONFIG_SYSTEM_CURL_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_CURL_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_CURL_STACKSIZE]
- [curl_main.c:struct curl_chunk_s]
- [curl_main.c:struct curl_body_s]
- [curl_main.c:struct curl_sink_s]
- [curl_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CURL]: Build and feature compilation gated by `CONFIG_SYSTEM_CURL`.
- [Kconfig:CONFIG_SYSTEM_CURL_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_CURL_PROGNAME`.
- [Kconfig:depends on NETUTILS_WEBCLIENT]: Requires Kconfig dependency condition `NETUTILS_WEBCLIENT`.
- [curl_main.c:CONFIG_SYSTEM_CURL_BUFFERSIZE]: Conditional compilation gated by `CONFIG_SYSTEM_CURL_BUFFERSIZE`.

## Side Effects
- [curl_main.c:close]: Performs VFS file or device descriptor I/O operations.
- [curl_main.c:free]: Allocates or releases dynamic heap memory.
- [curl_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
