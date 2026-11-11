# `industry/nxmodbus/core`

## Overview
Implements `industry/nxmodbus/core`: Create a new NxModbus instance. Input Parameters:

## Interface
- [nxmb_client.c:struct nxmb_client_state_s]
- [nxmb_client.c:nxmb_read_coils]
- [nxmb_client.c:nxmb_read_discrete]
- [nxmb_client.c:nxmb_read_input]
- [nxmb_client.c:nxmb_read_holding]
- [nxmb_client.c:nxmb_write_coil]
- [nxmb_client.c:nxmb_write_holding]
- [nxmb_client.c:nxmb_write_coils]
- [nxmb_client.c:nxmb_write_holdings]
- [nxmb_client.c:nxmb_readwrite_holdings]
- [nxmb_client.c:nxmb_set_timeout]
- [nxmb_client.c:nxmb_client_init]
- [nxmb_client.c:nxmb_client_deinit]
- [nxmb_context.c:nxmb_create]
- [nxmb_context.c:nxmb_destroy]
- [nxmb_context.c:nxmb_set_callbacks]
- [nxmb_context.c:nxmb_enable]
- [nxmb_context.c:nxmb_set_server_id]

## Invariants
- [nxmb_client.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && buf)` precondition.
- [nxmb_client.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx)` precondition.
- [nxmb_client.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && rd_buf && wr_buf)` precondition.
- [nxmb_client.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && ctx->client_state)` precondition.
- [nxmb_client.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && ctx->is_client)` precondition.
- [nxmb_client.c:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [nxmb_client.c:send]: Performs network socket creation, binding, or protocol I/O.
- [nxmb_client.c:calloc]: Allocates or releases dynamic heap memory.
- [nxmb_context.c:free]: Allocates or releases dynamic heap memory.
- [nxmb_func.c:malloc]: Allocates or releases dynamic heap memory.
- [nxmb_server.c:send]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
