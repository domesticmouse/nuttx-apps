# modules

## Overview
NuttX `fdpicxip/modules` component implementing `mkblobs.sh`.

## Interface
- `[mkblobs.sh:mkblobs.sh]` - Build helper script `mkblobs.sh <prefix> <module>...` generating C byte-array blobs from ELF FDPIC modules
- **callback**: [`./callback/README.md`](./callback/README.md) - NuttX `fdpicxip/modules/callback` component: Hands a module function to the firmware every way the firmware will accept one. In FDPIC a function pointer is the address of a two-word descriptor, not a code address, and that descriptor lives in the module's writable segment in RAM.  Firmware that stores such a pointer and later branches to it th
- **cxxuser**: [`./cxxuser/README.md`](./cxxuser/README.md) - NuttX `fdpicxip/modules/cxxuser` component: A C++ module using a C++ shared library. Two instances of this run at once in the demo.  Between them they show the three things that have to hold: - constructors ran, in both objects.  Neither magic can be right by accident: an unconstructed global is zero. - the library's constructors ran before t
- **funcdesc**: [`./funcdesc/README.md`](./funcdesc/README.md) - NuttX `fdpicxip/modules/funcdesc` component: Exercises R_ARM_FUNCDESC -- the relocation that asks the loader to manufacture a function descriptor and hand back its address. It is emitted for an *address-taken imported* function, which is a different thing from a called one.  A call gets a PLT entry and an R_ARM_FUNCDESC_VALUE relocation on a d
- **lazymod**: [`./lazymod/README.md`](./lazymod/README.md) - NuttX `fdpicxip/modules/lazymod` component: Built without -mlong-calls and linked with -z lazy (see the Makefile), so its imported function descriptors land in DT_JMPREL instead of DT_REL.
- **libcounter**: [`./libcounter/README.md`](./libcounter/README.md) - NuttX `fdpicxip/modules/libcounter` component: A shared library with its own state. g_calls is the interesting part: it lives in the library's writable segment.  Each task group that names this library in DT_NEEDED loads its own instance, so each has its own g_calls.  The library's code is mapped once and executed in place.
- **libshape**: [`./libshape/README.md`](./libshape/README.md) - NuttX `fdpicxip/modules/libshape` component: A C++ shared library, executed in place out of flash. The point of this file is g_registry.  It is a global object with a real constructor, and the constructor is the only thing that ever writes m_magic.  If the loader does not walk DT_INIT_ARRAY, the object simply stays in .bss and every field read
- **manyneeded**: [`./manyneeded/README.md`](./manyneeded/README.md) - NuttX `fdpicxip/modules/manyneeded` component: A module whose DT_NEEDED list is longer than the loader follows.  The loader refuses it before it loads any of the libraries, so the module never runs.
- **missingsym**: [`./missingsym/README.md`](./missingsym/README.md) - NuttX `fdpicxip/modules/missingsym` component: A module that imports a firmware symbol which does not exist.  It links cleanly -- the symbol simply becomes an undefined import resolved at load -- so the loader is the only thing that can catch it, when resolution fails rather than at link time.
- **need**: [`./need/README.md`](./need/README.md) - NuttX `fdpicxip/modules/need` component: A stub library.  Only its name matters, as an entry in DT_NEEDED.
- **qsorter**: [`./qsorter/README.md`](./qsorter/README.md) - NuttX `fdpicxip/modules/qsorter` component: Demonstrates the two things worth knowing about NuttX FDPIC modules. 1. qsort() runs in the firmware and calls back into compare(), which lives here.  That works because the firmware reserves the FDPIC register, so this module's data base survives the call in, and because libc resolves the callback 
- **user**: [`./user/README.md`](./user/README.md) - NuttX `fdpicxip/modules/user` component: Uses libcounter.so.  Two instances run concurrently.  Each instance is a task group with its own copy of the library data, so its total counts its own bumps.  The library text is shared. libcounter is also a *leaf* library -- it calls nothing outside itself, so it has no PLT and therefore no DT_PLTG

## Invariants
- `[mkblobs.sh:set -e]` - Halts immediately if any input binary is not an ARM FDPIC (`ET_DYN`, `EI_OSABI=65`) ELF module

## Side Effects
- `[mkblobs.sh:od]` - Reads ELF module binaries and prints generated C array definitions to stdout

## Verification
- Run: `make test`
