# `system/readline`

## Overview
Provides readline() Support (`system/readline`). Enable support for the readline() function.

## Interface
- [Kconfig:CONFIG_SYSTEM_READLINE]
- [Kconfig:CONFIG_READLINE_HAVE_EXTMATCH]
- [Kconfig:CONFIG_READLINE_ECHO]
- [Kconfig:CONFIG_READLINE_TABCOMPLETION]
- [readline.h:struct rl_common_s]
- [readline.h:readline_common]
- [readline.h:RL_GETC]
- [readline.h:RL_PUTC]
- [readline.h:RL_WRITE]
- [readline.c:readline]
- [readline_common.c:struct cmdhist_s]
- [readline_common.c:readline_prompt]
- [readline_common.c:readline_extmatch]
- [readline_common.c:readline_common]
- [readline_fd.c:struct readline_s]
- [readline_fd.c:readline_fd]
- [readline_fd.c:readline_fd_ex]
- [readline_stream.c:readline_stream]

## Invariants
- [Kconfig:CONFIG_SYSTEM_READLINE]: Build and feature compilation gated by `CONFIG_SYSTEM_READLINE`.
- [Kconfig:CONFIG_READLINE_HAVE_EXTMATCH]: Build and feature compilation gated by `CONFIG_READLINE_HAVE_EXTMATCH`.
- [Kconfig:depends on BUILTIN || READLINE_HAVE_EXTMATCH]: Requires Kconfig dependency condition `BUILTIN || READLINE_HAVE_EXTMATCH`.
- [Kconfig:depends on BUILTIN]: Requires Kconfig dependency condition `BUILTIN`.
- [Kconfig:depends on READLINE_HAVE_EXTMATCH]: Requires Kconfig dependency condition `READLINE_HAVE_EXTMATCH`.
- [readline.h:CONFIG_READLINE_ECHO]: Conditional compilation gated by `CONFIG_READLINE_ECHO`.

## Side Effects
- [readline.c:malloc]: Allocates or releases dynamic heap memory.
- [readline_fd.c:read]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
