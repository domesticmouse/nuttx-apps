# `netutils/chat`

## Overview
Provides Chat tool (`netutils/chat`). Enable the chat tool.

## Interface
- [Kconfig:CONFIG_NETUTILS_CHAT]
- [chat.h:enum chat_line_type]
- [chat.h:enum chat_command]
- [chat.h:struct chat_line]
- [chat.h:struct chat]
- [chat.h:lhs]
- [chat.c:struct chat_token]
- [chat.c:chat_init]
- [chat.c:chat]

## Invariants
- [Kconfig:CONFIG_NETUTILS_CHAT]: Build and feature compilation gated by `CONFIG_NETUTILS_CHAT`.
- [chat.c:DEBUGASSERT]: Enforces `DEBUGASSERT(priv != NULL && ctl != NULL && ctl->timeout >= 0)` precondition.
- [chat.c:DEBUGASSERT]: Enforces `DEBUGASSERT(script != NULL)` precondition.
- [chat.c:DEBUGASSERT]: Enforces `DEBUGASSERT(tok->string)` precondition.
- [chat.c:DEBUGASSERT]: Enforces `DEBUGASSERT(first_tok->string != NULL)` precondition.
- [chat.c:DEBUGASSERT]: Enforces `DEBUGASSERT(timeout_ms >= 0)` precondition.

## Side Effects
- [chat.c:read]: Performs VFS file or device descriptor I/O operations.
- [chat.c:malloc]: Allocates or releases dynamic heap memory.
- [chat.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
