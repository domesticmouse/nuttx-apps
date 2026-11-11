# `netutils/thttpd/cgi-src`

## Overview
Implements `netutils/thttpd/cgi-src` source and header components (`phf.c`, `redirect.c`, `ssi.c`) in the NuttX application tree.

## Interface
- [redirect.c:internal_error]
- [redirect.c:not_found]
- [redirect.c:moved]

## Invariants
- [phf.c:CONFIG_THTTPD_BINFS]: Conditional compilation gated by `CONFIG_THTTPD_BINFS`.
- [redirect.c:CONFIG_THTTPD_BINFS]: Conditional compilation gated by `CONFIG_THTTPD_BINFS`.
- [ssi.c:CONFIG_AUTH_FILE]: Conditional compilation gated by `CONFIG_AUTH_FILE`.
- [ssi.c:CONFIG_THTTPD_BINFS]: Conditional compilation gated by `CONFIG_THTTPD_BINFS`.

## Side Effects
- [phf.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [redirect.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [redirect.c:malloc]: Allocates or releases dynamic heap memory.
- [redirect.c:printf]: Writes formatted diagnostic, logging, or console output.
- [ssi.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [ssi.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
