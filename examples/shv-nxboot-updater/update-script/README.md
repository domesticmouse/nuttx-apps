# update-script

## Overview
NuttX `shv-nxboot-updater/update-script` component implementing `shvconfirm.py, shvflasher.py, tui.py`.

## Interface
- `[shvconfirm.py:class ConfirmStep]` - Python class `ConfirmStep`
- `[shvconfirm.py:shv_confirm]` - Python function `shv_confirm()`
- `[shvflasher.py:class FlashStep]` - Python class `FlashStep`
- `[shvflasher.py:shv_flasher]` - Python function `shv_flasher()`
- `[tui.py:get_parser]` - Python function `get_parser()`
- `[tui.py:do_flash]` - Python function `do_flash()`
- `[tui.py:do_confirm]` - Python function `do_confirm()`
- `[tui.py:tui_main]` - Python function `tui_main()`

## Invariants
- None

## Side Effects
- `[shvconfirm.py:SHVValueClient]` - Connects to SHV RPC broker over network to perform firmware updates/confirmation
- `[shvflasher.py:open]` - Opens local file or serial device for reading/writing
- `[shvflasher.py:SHVValueClient]` - Connects to SHV RPC broker over network to perform firmware updates/confirmation

## Verification
- Run: `make test`
