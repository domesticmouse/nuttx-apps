# `system/expat`

## Overview
Provides Expat XML parser (`system/expat`). Enable the Expat stream-oriented XML parser. The selected version is downloaded when the applications tree is configured.

## Interface
- [Kconfig:CONFIG_LIB_EXPAT]
- [Kconfig:CONFIG_LIB_EXPAT_VERSION]
- [Kconfig:CONFIG_LIB_EXPAT_CONTEXT_BYTES]
- [Kconfig:CONFIG_LIB_EXPAT_GENERAL_ENTITIES]
- [expat_config.h:BYTEORDER]
- [expat_config.h:WORDS_BIGENDIAN]
- [expat_config.h:HAVE_ARC4RANDOM_BUF]
- [expat_config.h:PACKAGE]
- [expat_config.h:PACKAGE_NAME]
- [expat_config.h:PACKAGE_STRING]
- [expat_config.h:PACKAGE_TARNAME]
- [expat_config.h:PACKAGE_URL]
- [expat_config.h:PACKAGE_VERSION]
- [expat_config.h:STDC_HEADERS]
- [expat_config.h:XML_CONTEXT_BYTES]
- [expat_config.h:XML_GE]

## Invariants
- [Kconfig:CONFIG_LIB_EXPAT]: Build and feature compilation gated by `CONFIG_LIB_EXPAT`.
- [Kconfig:CONFIG_LIB_EXPAT_VERSION]: Build and feature compilation gated by `CONFIG_LIB_EXPAT_VERSION`.
- [Kconfig:depends on ALLOW_MIT_COMPONENTS]: Requires Kconfig dependency condition `ALLOW_MIT_COMPONENTS`.
- [expat_config.h:CONFIG_ENDIAN_BIG]: Conditional compilation gated by `CONFIG_ENDIAN_BIG`.
- [expat_config.h:CONFIG_LIB_EXPAT_GENERAL_ENTITIES]: Conditional compilation gated by `CONFIG_LIB_EXPAT_GENERAL_ENTITIES`.

## Side Effects
- None

## Verification
- Run: `make test`
