# `include/builtin`

## Overview
Implements `include/builtin`: Executes builtin applications registered during 'make context' time. New application is run in a separate task context (and thread).

## Interface
- [builtin.h:exec_builtin]

## Invariants
- None

## Side Effects
- [builtin.h:exec_builtin]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
