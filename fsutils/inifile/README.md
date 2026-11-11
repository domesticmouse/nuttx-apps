# INI File Parser (`fsutils/inifile`)

## Overview
Implements a lightweight INI configuration file reader library (`CONFIG_FSUTILS_INIFILE`) supporting section navigation (`[section]`) and key-value string and integer lookups.

## Interface
- `[inifile.c:inifile_initialize]` / `[inifile.c:inifile_uninitialize]`: Opens an INI file and initializes/releases the parser state handle (`INIHANDLE`).
- `[inifile.c:inifile_read_string]` / `[inifile.c:inifile_free_string]`: Reads a newly allocated string value for a `(section, variable)` pair and frees it.
- `[inifile.c:inifile_read_integer]`: Reads and parses an integer value for a `(section, variable)` pair.
- `[Kconfig:FSUTILS_INIFILE]`, `[Kconfig:FSUTILS_INIFILE_MAXLINE]`, `[Kconfig:FSUTILS_INIFILE_DEBUGLEVEL]`: Build and line-length configuration options.

## Invariants
- `[inifile.c:CONFIG_FSUTILS_INIFILE_MAXLINE]`: Maximum line length per INI entry is bounded by `CONFIG_FSUTILS_INIFILE_MAXLINE` (default `256`).
- `[inifile.c:inifile_seek_to_section]`: Section headers must be at least 3 characters long and begin with `'['`; comment lines beginning with `';'` are ignored (`[inifile.c:inifile_read_noncomment_line]`).

## Side Effects
- `[inifile.c:inifile_initialize]` and `[inifile.c:inifile_uninitialize]`: Allocate/free parser state via `malloc`/`free` and open/close the target INI file via `fopen`/`fclose`.
- `[inifile.c:inifile_seek_to_section]`: Rewinds and reads lines from the open `FILE *` stream.
- `[inifile.c:inifile_read_string]` and `[inifile.c:inifile_free_string]`: Duplicate matched values via `strdup` and release them via `free`.

## Verification
- Run: `make test`
