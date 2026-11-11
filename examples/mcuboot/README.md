# mcuboot

## Overview
Intermediate grouping directory for `mcuboot`, organizing submodules: slot_confirm, swap_test, update_agent, update_agent_local.

## Subdirectories & Boundaries
- **slot_confirm**: [`./slot_confirm/README.md`](./slot_confirm/README.md) - MCUboot slot confirm example (`mcuboot/slot_confirm`). Example application for confirming a newly installed application application firmware image using MCUboot public APIs. This application should be used as the OTA update package of the EXAMPLES_MCUBOOT_UPDATE_AGENT example.
- **swap_test**: [`./swap_test/README.md`](./swap_test/README.md) - MCUboot SWAP Test image example (`mcuboot/swap_test`). Example application to demonstrate the firmware image swap and the image rollback processes of MCUboot using the boot swap and test method.
- **update_agent**: [`./update_agent/README.md`](./update_agent/README.md) - MCUboot update agent example (`mcuboot/update_agent`). Example application that implements an update agent that downloads an application firmware image from a given URL and saves it to the secondary slot as a pending update.
- **update_agent_local**: [`./update_agent_local/README.md`](./update_agent_local/README.md) - MCUBoot Local Update Agent (`mcuboot/update_agent_local`). Enable the MCUBoot Local Update Agent example. This application reads a firmware binary from local storage and copies it to the MCUBoot secondary flash slot for update.
