(C) 2024 Swudu Susuwu, dual licenses: choose [_GPLv2_](./LICENSE_GPLv2) or [_Apache 2_](./LICENSE) (allows all uses).
Cloned from <https://github.com/SwuduSusuwu/SusuLib/sh/>, scripts unrelated to [`.mid`](https://wikipedia.org/wiki/MIDI#Computer_files) removed.

# [Table of contents](../README.md#table-of-contents)
- [Purposes](#purposes)
- [Issues/workarounds](#issuesworkarounds)
# Purposes
[`./sh/`](./) is [`/bin/sh`](https://wikipedia.org/wiki/Bourne_shell) "scripts" / source code (for general use):
- [`./sh/Macros.sh`](./Macros.sh) is a standalone lib for common console tasks (can do most of what [ncurses](https://wikipedia.org/wiki/Ncurses) can do). `./build.sh` and `./sh/make.sh` use this.
  - Exports functions: {`SUSUWU_ECHO_COMMANDS()`, `SUSUWU_ESCAPE_SPACES()`, `SUSUWU_LOCAL_WORKSPACE_PATH()`, `SUSUWU_PATH_SHOULD_NOT_EXIST()`, `SUSUWU_PATH_SUFFIX_SLASH()`, `SUSUWU_PATH_UNAMBIGUOUS()`, `SUSUWU_PRINT()`, `SUSUWU_SH_HAS_PARAM()`, `SUSUWU_SH_REMOVE_PARAM()`, `SUSUWU_SH_<type-of-code>()`, `SUSUWU_SH_<warn-level>()`, `SUSUWU_ESCAPE_QUOTED()`}
  - Exports variables: {`SUSUWU_ABORT_ON_FIRST_ERROR`, `SUSUWU_ECHO_COMMANDS_TO`, `SUSUWU_S`, `SUSUWU_SH_CONSOLE_PARAMS`, `SUSUWU_SH_<color>`, `SUSUWU_VERBOSE`}
- [`./sh/Transcode.sh`](./Transcode.sh) is a standalone [`ffmpeg`](https://github.com/FFmpeg/FFmpeg)-based tool which goes with [`./posts/TranscodeMuxHowto.md`](../posts/TranscodeMuxHowto.md).

# Issues/workarounds
Issues:
- TODO: [produce alias (such as {`--silent`, `--quiet`} -> `-s`) groups of options/flags, for `SUSUWU_PROCESS_*` functions.](https://github.com/SwuduSusuwu/SusuLib/issues/23)
- TODO: [map options/flags (which `SUSUWU_PROCESS_*` functions use) to descriptions (for `--help` output.)](https://github.com/SwuduSusuwu/SusuLib/issues/24)

Workaround: [`git switch experimental`](../README.md#beta-testexperimental-builds)

