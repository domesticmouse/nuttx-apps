# libshape

## Overview
NuttX `fdpicxip/modules/libshape` component: A C++ shared library, executed in place out of flash. The point of this file is g_registry.  It is a global object with a real constructor, and the constructor is the only thing that ever writes m_magic.  If the loader does not walk DT_INIT_ARRAY, the object simply stays in .bss and every field read

## Interface
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `libshape`
- `[libshape.cpp:class Registry]` - C++ class `Registry`
- `[libshape.cpp:shape_add]` - Public function `shape_add()`
- `[libshape.cpp:shape_marker]` - Public function `shape_marker()`
- `[libshape.cpp:shape_total]` - Public function `shape_total()`
- `[libshape.cpp:shape_constructed]` - Public function `shape_constructed()`

## Invariants
- None

## Side Effects
- `[libshape.cpp:open]` - Opens device nodes or files via `open()`
- `[libshape.cpp:write]` - Writes bytes to file or device descriptors via `write()`
- `[libshape.cpp:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
