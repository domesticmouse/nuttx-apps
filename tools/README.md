# Application Build & Packaging Tools (`tools`)

## Overview
Contains host-side build scripts, symbol-table generators, Kconfig aggregation scripts, hash verification utilities, ROMFS/import archive scripts, bitmap converters, and WebAssembly (WASI-SDK) build rules used when configuring and compiling `apps/`.

## Interface
- `[apps/tools/mksymtab.sh:usage]` / `[apps/tools/mksymtab.sh:get_exec_list]`: Scans ELF binaries and thunk assembly files to emit C symbol table definitions (`struct symtab_s`).
- `[apps/tools/mkkconfig.sh:USAGE]`: Dynamically generates the top-level `apps/Kconfig` file from application subdirectories.
- `[apps/tools/check-hash.sh:usage]`: Verifies downloaded package archives against expected cryptographic digests.
- `[apps/tools/mkromfsimg.sh]`: Generates ROMFS C header images from directory trees using `genromfs` and `xxd`.
- `[apps/tools/mkimport.sh]`: Unpacks and populates `apps/import` from a NuttX kernel `make export` zip bundle.
- `[apps/tools/bitmap_converter.py]`: Converts bitmap images into NuttX NX graphics C header palettes and RLE pixel arrays.
- `[apps/tools/export_pkg_repo.py]`: Exports NuttX application packages into standalone repository structures.
- `[apps/tools/Wasm.mk:LINK_WASM]` / `[apps/tools/WASI-SDK.defs:WCC]` / `[apps/tools/Wasm/WASI-SDK.cmake:wasm_add_application]` / `[apps/tools/Wasm/WASI-SDK.cmake:wasm_add_library]`: Build system macros and CMake functions for compiling NuttX applications to WebAssembly (`.wasm`, `.aot`, `.xip`).

## Invariants
- `[apps/tools/mksymtab.sh:arg_count]`: Requires at least one `<imagedirpath>` argument and no unparsed trailing arguments after `getopts`.
- `[apps/tools/check-hash.sh:hash_algo]`: Requires 3 arguments (`<hash-algo> <expected-hash> <file-to-check>`), an existing target file, and `hash_algo` in `{sha1, sha224, sha256, sha384, sha512, md5}` unless `expected-hash` is empty, `"none"`, or `"skip"`.
- `[apps/tools/WASI-SDK.defs:WASM_BUILD]`: Forced to `"n"` if `$(WCC)` does not exist or if any of `CONFIG_ARCH_INTEL64`, `CONFIG_ARCH_SPARC_V8`, `CONFIG_ARCH_AVR`, or `CONFIG_ARCH_XTENSA` is enabled.
- `[apps/tools/Wasm/CMakeLists.txt:APPDIR]`, `[apps/tools/Wasm/CMakeLists.txt:TOPDIR]`, `[apps/tools/Wasm/CMakeLists.txt:TOPBINDIR]`, `[apps/tools/Wasm/CMakeLists.txt:KCONFIG_FILE_PATH]`, and `[apps/tools/Wasm/WASI-SDK.cmake:WASI_SDK_PATH]`: Must be defined or CMake halts with `FATAL_ERROR`.

## Side Effects
- `[apps/tools/mksymtab.sh:varlist]`: Invokes `find` and `nm` on target directories and writes generated C `struct symtab_s` source code to `stdout`.
- `[apps/tools/mkkconfig.sh:KCONFIG]`: Deletes and regenerates the target `Kconfig` file sourcing all `*/Kconfig` subdirectories.
- `[apps/tools/check-hash.sh:file_to_check]`: Deletes `${file_to_check}` via `rm -f` and exits with status `1` if the computed digest does not match the expected hash.
- `[apps/tools/Wasm.mk:WBIN]` and `[apps/tools/Wasm.mk:LINK_WASM]`: Compile C sources to `.wo` objects using WASI `clang`, archive them under `flock`, and emit `.wasm`/`.aot`/`.xip` binaries into `$(BINDIR)/wasm`.

## Verification
- Run: `make test`
