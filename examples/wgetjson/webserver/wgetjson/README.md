# wgetjson

## Overview
NuttX `wgetjson/webserver/wgetjson` component implementing `json_cmd.php, post_cmd.php`.

## Interface
- `[json_cmd.php:json_encode]` - PHP HTTP endpoint returning JSON-encoded payload
- `[post_cmd.php:json_encode]` - PHP HTTP endpoint returning JSON-encoded payload

## Invariants
- None

## Side Effects
- `[json_cmd.php:echo]` - Writes serialized JSON object to HTTP response stream
- `[post_cmd.php:$_POST]` - Echoes HTTP POST parameters as JSON to HTTP response stream

## Verification
- Run: `make test`
