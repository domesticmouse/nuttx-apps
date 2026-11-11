# Board-Specific Platform Extensions (`platform`)

## Overview
Provides the build integration point for board-specific user-space platform code (`apps/platform/board`), along with board-specific configuration data providers and a fallback dummy compilation unit.

## Subdirectories & Boundaries
- `dummy`: [./dummy/README.md](./dummy/README.md) - Fallback empty C translation unit ensuring non-empty static library creation when no board directory is linked.
- `mikroe-stm32f4`: [./mikroe-stm32f4/README.md](./mikroe-stm32f4/README.md) - Persistent configuration and touchscreen calibration storage implementation for the MikroElektronika STM32F4 board.
