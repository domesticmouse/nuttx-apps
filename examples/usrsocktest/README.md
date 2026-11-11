# usrsocktest

## Overview
USRSOCK test example (`usrsocktest`). Enable the User Socket test example. This example application runs unit-tests for /dev/usrsock.

## Interface
- `[defines.h:USRSOCK_NODE]` - Macro defining the usrsock character device path `"/dev/usrsock"`
- `[defines.h:struct usrsocktest_daemon_conf_s]` - Configuration structure for the mock usrsock daemon (`max_sockets`, `supported_domain`, `supported_type`, `supported_protocol`, `delay_all_responses`, `endpoint_block_connect`, `endpoint_block_send`, `endpoint_recv_avail_from_start`, `endpoint_recv_avail`, `endpoint_addr`, `endpoint_port`)
- `[usrsocktest_main.c:main]` - Application entry point that records heap `mallinfo` before and after running all test groups, prints summary statistics, and calls `exit(0)`
- `[usrsocktest_main.c:usrsocktest_assert_print_value]` - Public helper that increments `overall.nchecks`, compares two `long int` values while preserving `errno`, and prints assertion failure details on mismatch
- `[usrsocktest_main.c:usrsocktest_assert_print_buf]` - Public helper that increments `overall.nchecks`, compares two buffers with `memcmp` while preserving `errno`, and prints assertion failure details on mismatch
- `[usrsocktest_daemon.c:usrsocktest_daemon_start]` - Starts the mock usrsock daemon pthread and control pipe using `struct usrsocktest_daemon_conf_s`
- `[usrsocktest_daemon.c:usrsocktest_daemon_stop]` - Stops the mock usrsock daemon thread, joins delayed command threads, frees remaining socket endpoints, and closes the control pipe
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_num_active_sockets]` - Returns the count of currently opened test sockets in the daemon
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_num_connected_sockets]` - Returns the count of connected test sockets in the daemon
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_num_waiting_connect_sockets]` - Returns the count of test sockets waiting in a blocked connect state
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_num_recv_empty_sockets]` - Returns the count of active test sockets with zero available receive bytes
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_send_bytes]` - Returns total bytes sent across test sockets in the daemon
- `[usrsocktest_daemon.c:usrsocktest_daemon_get_recv_bytes]` - Returns total bytes received across test sockets in the daemon
- `[usrsocktest_daemon.c:usrsocktest_daemon_pause_usrsock_handling]` - Pauses or resumes polling of `/dev/usrsock` in the daemon thread
- `[usrsocktest_daemon.c:usrsocktest_send_delayed_command]` - Spawns a helper pthread to write a single-character control command to the daemon pipe after `delay_msec`
- `[usrsocktest_daemon.c:usrsocktest_daemon_establish_waiting_connections]` - Convenience wrapper calling `usrsocktest_send_delayed_command('E', 0)` to establish blocked connections

## Invariants
- `[usrsocktest_daemon.c:TEST_SOCKET_SOCKID_BASE]` - Daemon-assigned `usockid` values start at `10000U` and are bounded by `TEST_SOCKET_COUNT` (8 slots); `test_socket_get` rejects IDs outside `[10000, 10007]`
- `[usrsocktest_daemon.c:find_endpoint]` - Asserts via `DEBUGASSERT` that `malloc(sizeof(*endpaddr))` succeeds and `inet_pton(AF_INET, priv->conf->endpoint_addr, ...)` returns non-zero
- `[usrsocktest_daemon.c:usrsocktest_daemon_start]` - Only one daemon instance can run at a time; returns `-EALREADY` if `priv->conf != NULL` or `!priv->joined` under `daemon_mutex`
- `[usrsocktest_chardev.c:no_multiple_open]` - `/dev/usrsock` allows only a single open descriptor at a time; a second concurrent `open()` fails with `EPERM`
- `[usrsocktest_basic_daemon.c:open_close]` - After stopping the daemon, `usrsocktest_endp_malloc_cnt` and `usrsocktest_dcmd_malloc_cnt` must both equal 0

## Side Effects
- `[usrsocktest_daemon.c:usrsocktest_daemon]` - Opens `"/dev/usrsock"` with `O_RDWR`, polls `/dev/usrsock` and an internal command pipe, reads usrsock request headers/payloads, and writes usrsock responses and socket events back to `/dev/usrsock`
- `[usrsocktest_daemon.c:usrsocktest_daemon_start]` - Mutates global `g_ub_daemon` state, creates an OS pipe (`priv->pipefd`), initializes `priv->wakewaitsem`, and spawns the `usrsocktest_daemon` pthread
- `[usrsocktest_daemon.c:usrsocktest_daemon_stop]` - Joins all queued `delayed_cmd_threads`, writes `'S'` to the daemon pipe, joins the daemon pthread, frees unclosed socket endpoint allocations, and closes pipe file descriptors
- `[usrsocktest_wake_with_signal.c:do_wake_test]` - Installs a `SIGUSR1` signal handler via `sigaction`, spawns up to 4 worker pthreads, and sends `SIGUSR1` via `pthread_kill` or cancels threads via `pthread_cancel`

## Verification
- Run: `make test`
