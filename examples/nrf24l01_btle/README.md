# nrf24l01_btle

## Overview
Use nRF24L01 emulates a nRF8001 temperature beacon (`nrf24l01_btle`). Emulates a nRF8001 temperature beacon,reads temperature from a DHT11 and sends it via BTLE.Compatible with Nordic Semiconductor apps such as nRF Master Control Panel or nRF Temp 2.0.

## Interface
- `[Kconfig:EXAMPLES_NRF24L01_BTLE]` - Build configuration option `EXAMPLES_NRF24L01_BTLE`
- `[Kconfig:EXAMPLES_NRF24L01_BTLE_PROGNAME]` - Build configuration option `EXAMPLES_NRF24L01_BTLE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NRF24L01_BTLE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NRF24L01_BTLE_PROGNAME}`
- `[nrf24l01_btle.h:struct nrf_service_data]` - Structure definition `nrf_service_data`
- `[nrf24l01_btle.h:struct btle_adv_pdu]` - Structure definition `btle_adv_pdu`
- `[nrf24l01_btle.h:struct btle_pdu_chunk]` - Structure definition `btle_pdu_chunk`
- `[nrf24l01_btle.h:nrf24_cfg]` - Public function declaration `nrf24_cfg()`
- `[nrf24l01_btle.h:nrf24_open]` - Public function declaration `nrf24_open()`
- `[nrf24l01_btle.h:nrf24_send]` - Public function declaration `nrf24_send()`
- `[nrf24l01_btle.c:swapbits]` - Public function `swapbits()`
- `[nrf24l01_btle.c:nrf24_cfg]` - Public function `nrf24_cfg()`
- `[nrf24l01_btle.c:nrf24_open]` - Public function `nrf24_open()`
- `[nrf24l01_btle.c:nrf24_send]` - Public function `nrf24_send()`
- `[nrf24l01_btle.c:advertise]` - Public function `advertise()`
- `[nrf24l01_btle.c:nrf24_read]` - Public function `nrf24_read()`
- `[nrf24l01_btle.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DRIVERS_WIRELESS]` - Requires kernel/app configuration `DRIVERS_WIRELESS`
- `[Kconfig:depends on SENSORS_DHTXX]` - Requires kernel/app configuration `SENSORS_DHTXX`
- `[nrf24l01_btle.c:CONFIG_DEBUG_WIRELESS]` - Configuration guard on `CONFIG_DEBUG_WIRELESS`
- `[nrf24l01_btle.c:CONFIG_WL_NRF24L01_RXSUPPORT]` - Configuration guard on `CONFIG_WL_NRF24L01_RXSUPPORT`
- `[nrf24l01_btle.c:CONFIG_NRF24L01_BTLE_DHT11]` - Configuration guard on `CONFIG_NRF24L01_BTLE_DHT11`

## Side Effects
- `[nrf24l01_btle.c:/dev/hum0]` - Opens or interacts with VFS/device path `/dev/hum0`
- `[nrf24l01_btle.c:/dev/nrf24l01]` - Opens or interacts with VFS/device path `/dev/nrf24l01`
- `[nrf24l01_btle.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[nrf24l01_btle.c:open]` - Opens device nodes or files via `open()`
- `[nrf24l01_btle.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nrf24l01_btle.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nrf24l01_btle.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[nrf24l01_btle.c:syslog]` - Writes diagnostic log entries via `syslog()`
- `[nrf24l01_btle.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
