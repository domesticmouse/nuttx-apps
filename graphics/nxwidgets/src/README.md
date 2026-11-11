# `graphics/nxwidgets/src`

## Overview
Implements `graphics/nxwidgets/src` source and header components (`cbgwindow.cxx`, `cbitmap.cxx`, `cbutton.cxx`, `cbuttonarray.cxx` and 54 more files) in the NuttX application tree.

## Interface
- [cnumericedit.cxx:class CDraggableLabel]
- [crect.cxx:fromCoordinates]

## Invariants
- [cbuttonarray.cxx:CONFIG_NX_WRITEONLY]: Conditional compilation gated by `CONFIG_NX_WRITEONLY`.
- [ccallback.cxx:DEBUGASSERT]: Enforces `DEBUGASSERT(windowType == NXTK_FRAMEDWINDOW)` precondition.
- [ccallback.cxx:DEBUGASSERT]: Enforces `DEBUGASSERT(ret >= 0 || errno == EINTR)` precondition.
- [ccallback.cxx:DEBUGASSERT]: Enforces `DEBUGASSERT(This != NULL)` precondition.
- [ccallback.cxx:sem_wait]: Synchronizes concurrent access across threads or critical sections.
- [ccallback.cxx:CONFIG_NXTERM_NXKBDIN]: Conditional compilation gated by `CONFIG_NXTERM_NXKBDIN`.

## Side Effects
- [cbgwindow.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cnxserver.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cnxserver.cxx:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [cnxtkwindow.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cnxtoolbar.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cnxwidget.cxx:close]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
