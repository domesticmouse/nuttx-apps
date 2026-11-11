# NuttShell Library (`nshlib`)

## Overview
Implements the core NuttShell (NSH) library (`CONFIG_NSH_LIBRARY`), providing command parsing, built-in and file-based command execution, scripting (`if`/`then`/`else`/`fi` and `while`/`until`/`do`/`done`), environment and local variable management, aliases, serial/USB/Telnet/alternate console front ends, login authentication, and system initialization hooks.

## Interface
- `[apps/nshlib/nsh_init.c:nsh_initialize]`: Initializes the NSH subsystem, symbol tables, startup scripts, network bringup, and Telnet/SSH daemons.
- `[apps/nshlib/nsh_consolemain.c:nsh_consolemain]`: Main loop entry point for serial or standard I/O console sessions.
- `[apps/nshlib/nsh_telnetd.c:nsh_telnetstart]` / `[apps/nshlib/nsh_telnetd.c:nsh_telnetmain]`: Starts and handles Telnet NSH daemon sessions.
- `[apps/nshlib/nsh_system.c:nsh_system]` / `[apps/nshlib/nsh_system.c:nsh_system_ctty]`: Executes a single command string via the NSH parser.
- `[apps/nshlib/nsh_console.c:nsh_newconsole]`: Allocates and initializes a `struct console_stdio_s` console vtable instance.
- `[apps/nshlib/nsh_session.c:nsh_session]`: Runs an interactive NSH login and command read-eval loop on a console state.
- `[apps/nshlib/nsh_parse.c:nsh_parse]`: Tokenizes, expands variables/aliases, handles redirection, and dispatches a command line.
- `[apps/nshlib/nsh_command.c:nsh_command]` / `[apps/nshlib/nsh_command.c:nsh_extmatch_count]` / `[apps/nshlib/nsh_command.c:nsh_extmatch_getname]`: Dispatches internal NSH commands and provides command tab-completion matching.
- `[apps/nshlib/nsh_script.c:nsh_script]` / `[apps/nshlib/nsh_script.c:nsh_sysinitscript]` / `[apps/nshlib/nsh_script.c:nsh_initscript]` / `[apps/nshlib/nsh_script.c:nsh_loginscript]`: Executes NSH script files from the filesystem or ROMFS startup paths.
- `[apps/nshlib/nsh_builtin.c:nsh_builtin]` and `[apps/nshlib/nsh_fileapps.c:nsh_fileapp]`: Execute registered built-in applications and PATH-resolved file applications.
- `[apps/nshlib/nsh_prompt.c:nsh_prompt]` / `[apps/nshlib/nsh_prompt.c:nsh_update_prompt]`: Queries and updates the active NSH prompt string.
- `[apps/nshlib/nsh_login.c:nsh_login]` / `[apps/nshlib/nsh_telnetlogin.c:nsh_telnetlogin]` / `[apps/nshlib/nsh_identity.c:nsh_setuser_identity]`: Authenticate console/Telnet users and apply user identity credentials.
- `[apps/nshlib/nsh_vars.c:nsh_getvar]` / `[apps/nshlib/nsh_vars.c:nsh_setvar]` / `[apps/nshlib/nsh_vars.c:nsh_unsetvar]` / `[apps/nshlib/nsh_vars.c:nsh_foreach_var]`: Manage NSH session variables.
- `[apps/nshlib/nsh_alias.c:nsh_aliasfind]` / `[apps/nshlib/nsh_alias.c:nsh_aliasfree]`: Resolve and release shell command aliases.
- `[apps/nshlib/nsh_envcmds.c:nsh_getcwd]` / `[apps/nshlib/nsh_envcmds.c:nsh_getfullpath]` / `[apps/nshlib/nsh_envcmds.c:nsh_freefullpath]`: Resolve working directories and full VFS paths.
- `[apps/nshlib/nsh_fsutils.c:nsh_catfile]` / `[apps/nshlib/nsh_fsutils.c:nsh_readfile]` / `[apps/nshlib/nsh_fsutils.c:nsh_writefile]` / `[apps/nshlib/nsh_fsutils.c:nsh_foreach_direntry]`: Filesystem inspection and manipulation helpers.
- `[apps/nshlib/nsh_console.h:struct nsh_vtbl_s]`, `[apps/nshlib/nsh_console.h:struct console_stdio_s]`, `[apps/nshlib/nsh.h:struct nsh_parser_s]`, `[apps/nshlib/nsh.h:nsh_cmd_t]`: Core NSH console virtual table and parser state structures.

## Invariants
- `[apps/nshlib/nsh.h:CONFIG_NSH_CONSOLE]` or `[apps/nshlib/nsh.h:CONFIG_NSH_TELNET]` must be defined; otherwise compilation fails with `#error "No NSH front end defined"`.
- `[apps/nshlib/nsh_console.h:CONFIG_NSH_ALTCONDEV]` requires at least one of `CONFIG_NSH_ALTSTDIN`, `CONFIG_NSH_ALTSTDOUT`, or `CONFIG_NSH_ALTSTDERR` to be defined.
- `[apps/nshlib/nsh.h:IOBUFFERSIZE]` is enforced to be at least `PATH_MAX + 1` (or `1024` if `CONFIG_NSH_FILEIOSIZE` is not set and `NSH_HAVE_IOBUFFER` is defined).
- `[apps/nshlib/nsh.h:CONFIG_NSH_MAXARGUMENTS]` is raised to at least `11` when `CONFIG_NET` is enabled and `CONFIG_NSH_DISABLE_IFCONFIG` is not defined; `[apps/nshlib/nsh.h:MAX_ARGV_ENTRIES]` is `CONFIG_NSH_MAXARGUMENTS + 5` (or `+ 4` when `CONFIG_NSH_DISABLEBG` is defined).
- `[apps/nshlib/nsh.h:CONFIG_NSH_NESTDEPTH]` bounds the maximum nesting depth of `if-then-else-fi` (`np_iestate`) and `while/until-do-done` (`np_lpstate`) blocks.
- `[apps/nshlib/nsh_consolemain.c:nsh_consolemain]`, `[apps/nshlib/nsh_session.c:nsh_session]`, `[apps/nshlib/nsh_system.c:nsh_system_]`, and `[apps/nshlib/nsh_telnetd.c:nsh_telnetmain]` assert `pstate != NULL` via `DEBUGASSERT`.
- `[apps/nshlib/nsh_script.c:nsh_initscript]` executes once per boot guarded by `g_nsh_script_initialized` under `sched_lock()` / `sched_unlock()`.

## Side Effects
- `[apps/nshlib/nsh_init.c:nsh_initialize]`: Configures readline prompts and tab-completion vtables, enables USB trace (`usbtrace_enable`), registers the application symbol table via `boardctl(BOARDIOC_APP_SYMTAB)`, mounts/runs ROMFS startup scripts, brings up networking via `netinit_bringup()`, and starts Telnet (`nsh_telnetstart`) and Dropbear (`nsh_dropbearstart`) daemons.
- `[apps/nshlib/nsh_console.c:nsh_newconsole]` and `[apps/nshlib/nsh_console.c:nsh_consoleexit]`: Allocate and release `struct console_stdio_s` heap state, bind/close file descriptors, and terminate calling tasks via `exit()`.
- `[apps/nshlib/nsh_session.c:nsh_session]`: Authenticates users, writes MOTD/greetings, mutates terminal `ECHO` `termios` flags via `tcgetattr`/`tcsetattr`, and executes commands in an interactive loop.
- `[apps/nshlib/nsh_builtin.c:nsh_builtin]` and `[apps/nshlib/nsh_fileapps.c:nsh_fileapp]`: Lock the scheduler via `sched_lock()`, spawn tasks via `exec_builtin()` or `posix_spawnp()`, set controlling terminals via `TIOCSCTTY` `ioctl`, and block on foreground children via `waitpid()`.

## Verification
- Run: `make test`
