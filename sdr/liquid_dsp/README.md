# Liquid-DSP Integration (`sdr/liquid_dsp`)

## Overview
Provides the build configuration and static `config.h` platform header for integrating the `liquid-dsp` software-defined radio digital signal processing library (`CONFIG_SDR_LIQUID_DSP`) into NuttX.

## Interface
- `[Kconfig:CONFIG_SDR_LIQUID_DSP]`: Enables building the `liquid-dsp` library.
- `[config.h:PACKAGE_NAME]`, `[config.h:PACKAGE_VERSION]`, `[config.h:SIZEOF_INT]`, `[config.h:SIZEOF_LONG_INT]`, `[config.h:SIZEOF_LONG_LONG_INT]`, `[config.h:SIZEOF_SHORT_INT]`: Preconfigured autoconf macros for NuttX targets.
- `[Makefile:M_SQRT1_2]`, `[Makefile:M_SQRT2]`, `[Makefile:M_PI]`, `[Makefile:M_LN2]`, `[Makefile:M_PI_2]`, `[Makefile:M_2_PI]`: Math constant definitions passed when compiling `liquid-dsp`.

## Invariants
- `[config.h:HAVE_AVX]`: Host x86 SIMD extensions (`HAVE_AVX`, `HAVE_MMX`, `HAVE_SSE`, `HAVE_SSE2`, `HAVE_SSE3`, `HAVE_SSE41`, `HAVE_SSE42`, `HAVE_SSSE3`) are fixed to `0`.
- `[config.h:SIZEOF_INT]`: Assumes 32-bit `int` (`4`), 64-bit `long int` (`8`), 64-bit `long long int` (`8`), and 16-bit `short int` (`2`).

## Side Effects
- `[Makefile:$(LIQUID_DSP_TARBALL)]`: Downloads the `liquid-dsp` v1.4.0 tarball from GitHub via `curl` and unpacks it into `liquid-dsp` during build context setup.

## Verification
- Run: `make test`
