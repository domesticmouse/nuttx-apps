# NxBoot Image Generation Tool (`boot/nxboot/tools`)

## Overview
Provides the Python host utility (`nximage.py`) for prepending a NuttX Bootloader (`nxboot`) image header—including magic bytes, Semantic Versioning 2.0.0 metadata, platform identifier, payload size, and CRC32 checksum—to a compiled firmware binary.

## Interface
- `[nximage.py:NxImage]` / `[nximage.py:NxImage.add_header]`: Class encapsulating firmware image metadata and generating the header-prefixed output image.
- `[nximage.py:parse_args]` / `[nximage.py:main]`: CLI argument parser and entrypoint for generating `nxboot` images.

## Invariants
- `[nximage.py:NxImage.__init__]` and `[nximage.py:NxImage.add_header]`: Require a valid Semantic Versioning 2.0.0 string parsed by `semantic_version.Version` and `header_size >= 128` bytes (`self.header_size - 128` padding bytes of `0xff` are appended after the 128-byte fixed header).
- `[nximage.py:NxImage.add_header]`: Writes header magic `b"\x4e\x58\x4f\x53"` (`0x534f584e` little-endian) and computes `zlib.crc32` over the output file starting from byte offset 12, storing the 32-bit little-endian CRC at byte offset 8.

## Side Effects
- `[nximage.py:NxImage.add_header]` and `[nximage.py:main]`: Open input binary `self.path` (`r+b`), create/overwrite output image `self.result` (`w+b` and `r+b`) with the prepended header and CRC32, and print image metadata to `stdout` when `-v` is enabled.

## Verification
- Run: `make test`
