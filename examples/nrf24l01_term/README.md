# nrf24l01_term

## Overview
Basic nRF24L01 terminal (`nrf24l01_term`).

## Interface
- `[Kconfig:EXAMPLES_NRF24L01TERM]` - Build configuration option `EXAMPLES_NRF24L01TERM`
- `[Makefile:PROGNAME]` - Registers application/module target `nrf24l01_term`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nrf24l01_term`
- `[nrf24l01_term.c:wireless_cfg]` - Public function `wireless_cfg()`
- `[nrf24l01_term.c:wireless_open]` - Public function `wireless_open()`
- `[nrf24l01_term.c:send_pkt]` - Public function `send_pkt()`
- `[nrf24l01_term.c:read_pkt]` - Public function `read_pkt()`
- `[nrf24l01_term.c:usage]` - Public function `usage()`
- `[nrf24l01_term.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DRIVERS_WIRELESS]` - Requires kernel/app configuration `DRIVERS_WIRELESS`
- `[nrf24l01_term.c:CONFIG_WL_NRF24L01_RXSUPPORT]` - Configuration guard on `CONFIG_WL_NRF24L01_RXSUPPORT`
- `[nrf24l01_term.c:CONFIG_SYSTEM_READLINE]` - Configuration guard on `CONFIG_SYSTEM_READLINE`

## Side Effects
- `[nrf24l01_term.c:/dev/nrf24l01]` - Opens or interacts with VFS/device path `/dev/nrf24l01`
- `[nrf24l01_term.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[nrf24l01_term.c:open]` - Opens device nodes or files via `open()`
- `[nrf24l01_term.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nrf24l01_term.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[nrf24l01_term.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
