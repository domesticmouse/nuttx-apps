# `interpreters/berry/include`

## Overview
Implements `interpreters/berry/include` source and header components (`berry_conf.h`) in the NuttX application tree.

## Interface
- [berry_conf.h:BE_DEBUG]
- [berry_conf.h:BE_INTGER_TYPE]
- [berry_conf.h:BE_USE_SINGLE_FLOAT]
- [berry_conf.h:BE_BYTES_MAX_SIZE]
- [berry_conf.h:BE_USE_PRECOMPILED_OBJECT]
- [berry_conf.h:BE_DEBUG_SOURCE_FILE]
- [berry_conf.h:BE_DEBUG_RUNTIME_INFO]
- [berry_conf.h:BE_DEBUG_VAR_INFO]
- [berry_conf.h:BE_USE_PERF_COUNTERS]
- [berry_conf.h:BE_VM_OBSERVABILITY_SAMPLING]
- [berry_conf.h:BE_STACK_TOTAL_MAX]
- [berry_conf.h:BE_STACK_FREE_MIN]
- [berry_conf.h:BE_STACK_START]
- [berry_conf.h:BE_CONST_SEARCH_SIZE]
- [berry_conf.h:BE_USE_STR_HASH_CACHE]
- [berry_conf.h:BE_USE_FILE_SYSTEM]

## Invariants
- [berry_conf.h:assert]: Enforces `assert(expr)` precondition.

## Side Effects
- None

## Verification
- Run: `make test`
