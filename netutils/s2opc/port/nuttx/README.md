# `netutils/s2opc/port/nuttx`

## Overview
Implements `netutils/s2opc/port/nuttx` source and header components (`p_sopc_askpass.c`, `p_sopc_atomic.c`, `p_sopc_date_time.c`, `p_sopc_eth_sockets.c` and 12 more files) in the NuttX application tree.

## Interface
- [p_sopc_sockets.h:struct SOPC_Socket_Impl]
- [p_sopc_sockets.h:struct SOPC_Socket_AddressInfo]
- [p_sopc_sockets.h:struct SOPC_Socket_Address]
- [p_sopc_sockets.h:struct SOPC_SocketSet]
- [p_sopc_threads.h:struct SOPC_Mutex_Impl]
- [p_sopc_threads.h:struct SOPC_Condition_Impl]
- [p_sopc_threads.h:struct SOPC_Thread_Impl]
- [s2opc_common_export.h:S2OPC_COMMON_EXPORT]
- [s2opc_common_export.h:S2OPC_COMMON_NO_EXPORT]
- [s2opc_common_export.h:S2OPC_COMMON_DEPRECATED]
- [s2opc_common_export.h:S2OPC_COMMON_DEPRECATED_EXPORT]
- [s2opc_common_export.h:S2OPC_COMMON_DEPRECATED_NO_EXPORT]
- [sopc_nuttx_config.h:IPV6_ADD_MEMBERSHIP]
- [sopc_nuttx_config.h:IPV6_DROP_MEMBERSHIP]
- [sopc_nuttx_config.h:SOPC_MAX_NB_ELEMENTS_ASYNC_QUEUE_WARNING_ONLY]
- [sopc_nuttx_config.h:SOPC_HAS_FILESYSTEM]
- [p_sopc_askpass.c:SOPC_AskPass_CustomPromptFromTerminal]
- [p_sopc_atomic.c:SOPC_Atomic_Int_Get]

## Invariants
- [sopc_nuttx_config.h:CONFIG_S2OPC_NODE_MANAGEMENT]: Conditional compilation gated by `CONFIG_S2OPC_NODE_MANAGEMENT`.
- [sopc_nuttx_config.h:CONFIG_S2OPC_NODE_ADD_OPTIONAL]: Conditional compilation gated by `CONFIG_S2OPC_NODE_ADD_OPTIONAL`.
- [sopc_nuttx_config.h:CONFIG_S2OPC_HISTORY_READ]: Conditional compilation gated by `CONFIG_S2OPC_HISTORY_READ`.
- [sopc_nuttx_config.h:CONFIG_S2OPC_EVENT_MANAGEMENT]: Conditional compilation gated by `CONFIG_S2OPC_EVENT_MANAGEMENT`.
- [sopc_nuttx_config.h:CONFIG_S2OPC_AUDITING]: Conditional compilation gated by `CONFIG_S2OPC_AUDITING`.
- [p_sopc_eth_sockets.c:CONFIG_S2OPC_ETHERNET]: Conditional compilation gated by `CONFIG_S2OPC_ETHERNET`.

## Side Effects
- [p_sopc_eth_sockets.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [p_sopc_eth_sockets.c:close]: Performs VFS file or device descriptor I/O operations.
- [p_sopc_eth_sockets.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [p_sopc_filesystem.c:mkdir]: Performs VFS file or device descriptor I/O operations.
- [p_sopc_mem_alloc.c:malloc]: Allocates or releases dynamic heap memory.
- [p_sopc_sockets.c:ioctl]: Issues device/driver control requests via `ioctl()`.

## Verification
- Run: `make test`
