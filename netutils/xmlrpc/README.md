# `netutils/xmlrpc`

## Overview
Provides XML RPC library (`netutils/xmlrpc`). Enables the Embeddable Lightweight XML-RPC Server discussed at http://www.drdobbs.com/web-development/an-embeddable-lightweight-xml-rpc-server/184405364

## Interface
- [Kconfig:CONFIG_NETUTILS_XMLRPC]
- [Kconfig:CONFIG_XMLRPC_STRINGSIZE]
- [response.c:xmlrpc_getinteger]
- [response.c:xmlrpc_getbool]
- [response.c:xmlrpc_getdouble]
- [response.c:xmlrpc_getstring]
- [response.c:xmlrpc_buildresponse]
- [xmlparser.c:struct parsebuf_s]
- [xmlparser.c:xmlrpc_parse]
- [xmlparser.c:xmlrpc_register]

## Invariants
- [Kconfig:CONFIG_NETUTILS_XMLRPC]: Build and feature compilation gated by `CONFIG_NETUTILS_XMLRPC`.
- [Kconfig:CONFIG_XMLRPC_STRINGSIZE]: Build and feature compilation gated by `CONFIG_XMLRPC_STRINGSIZE`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.

## Side Effects
- [xmlparser.c:send]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
