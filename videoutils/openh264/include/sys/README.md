# OpenH264 System Header Stubs (`videoutils/openh264/include/sys`)

## Overview
Provides a compatibility stub header (`sys/sysctl.h`) required to compile the OpenH264 codec library on NuttX targets where BSD `sysctl` system calls are not present.

## Interface
- `[sysctl.h:sysctl]`: Stub macro for `sysctl` returning `-1`.
- `[sysctl.h:sysctlbyname]`: Stub macro for `sysctlbyname` returning `-1`.
- `[sysctl.h:sysctlnametomib]`: Stub macro for `sysctlnametomib` returning `-1`.

## Invariants
- `[sysctl.h:sysctl]`, `[sysctl.h:sysctlbyname]`, and `[sysctl.h:sysctlnametomib]` unconditionally evaluate to `(-1)` as no-op compatibility macros.

## Side Effects
- None

## Verification
- Run: `make test`
