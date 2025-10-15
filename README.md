(C) 2024 Swudu Susuwu, dual licenses: choose [_GPLv2_](./LICENSE_GPLv2) or [_Apache 2_](./LICENSE) (allows all uses).

# Table of Contents
- [Purposes](#purposes)
- [How to use this](#how-to-use-this)
  - [Download](#download)
  - [Signatures / certificates](#signatures--certificates)
- [How to contribute](./CONTRIBUTING.md#how-to-contribute)
  - [Beta tests / `preview` branch](./CONTRIBUTING.md#beta-tests--preview-branch)
  - [Good first issues to contribute to](https://github.com/SwuduSusuwu/SusuMid/contribute)
  - [Contributor conventions / rules](./CONTRIBUTING.md#contributor-conventions--rules)
    - [_Markdown_](./CONTRIBUTING.md#markdown)
    - [`git`](./CONTRIBUTING.md#git)
    - [`sh` source](./CONTRIBUTING.md#sh-source)
  - [Sponsor](./CONTRIBUTING.md#sponsor)
    - [Escrow](./CONTRIBUTING.md#escrow)
    - [Affiliates](./CONTRIBUTING.md#affiliates)
  - [Tools used](./CONTRIBUTING.md#tools-used)
  - [Contributors / sponsors](./CONTRIBUTING.md#contributors--sponsors)

# Purposes
[`./.ssh/`](./.ssh/) is to [use signatures / certificates](#signatures--certificates).

[`./mid/`](./mid/) stages [`.mid`](https://wikipedia.org/wiki/MIDI#Computer_files) sound (music) samples for <https://swudususuwu.substack.com/podcast>, which includes <https://github.com/SwuduSusuwu/SusuPosts/blob/preview/posts/SakuraSchoolHowto.md> (plus most of [_SusuMid_ on _Youtube_ (all are allowed to use the `.opus` versions from _Youtube_, just give attribution if you want to)](https://www.youtube.com/watch?v=jbyE0W4FFjA&list=PLTYe2PlBb7aeNRwaNvbvpqFsoCa5S6fyx&index=2)).
- Much of those were not stored as `.mid`, and the few that were sound best if opened with [_Perfect Piano_](https://play.google.com/store/apps/details?id=com.gamestar.perfectpiano&hl=en-US) with the instrument from the filename.
- The filenames are formatted as `YYMMDDHHMM[SS]_Instrument[_Title].mid` (`<[ISO 8601:2004](https://www.iso.org/standard/40874.html)>_<Instrument>[_<Title>]`, `<*>` is variable and `[*]` is optional).

[`./posts/`](./posts/) stages posts (virtual schools) for <https://SwuduSusuwu.SubStack.com/> about: artificial neural tissue, antiviruses, assistants, plus autonomous tools.
- [`./posts/TranscodeMuxHowto.md`](./posts/TranscodeMuxHowto.md) is simple [`/bin/sh`](https://wikipedia.org/wiki/Bourne_shell) commands for advanced [`ffmpeg`](https://wikipedia.org/wiki/FFmpeg) use (formulas to encode visuals relate to [issue #2](https://github.com/SwuduSusuwu/SusuLib/issues/2#issuecomment-2110726542)).

[`./sh/`](./sh/) is [`/bin/sh`](https://wikipedia.org/wiki/Bourne_shell) "scripts" / source code (produced for `./build.sh` and for general use):.
- [`./sh/Macros.sh`](./sh/Macros.sh) is a standalone lib for common console tasks (can do most of what [ncurses](https://wikipedia.org/wiki/Ncurses) can do). `./build.sh` and `./sh/make.sh` use this.
  - Exports functions: {`SUSUWU_ECHO_COMMANDS()`, `SUSUWU_ESCAPE_SPACES()`, `SUSUWU_LOCAL_WORKSPACE_PATH()`, `SUSUWU_PATH_SHOULD_NOT_EXIST()`, `SUSUWU_PATH_SUFFIX_SLASH()`, `SUSUWU_PATH_UNAMBIGUOUS()`, `SUSUWU_PRINT()`, `SUSUWU_SH_HAS_PARAM()`, `SUSUWU_SH_REMOVE_PARAM()`, `SUSUWU_SH_<type-of-code>()`, `SUSUWU_SH_<warn-level>()`, `SUSUWU_ESCAPE_QUOTED()`}
  - Exports variables: {`SUSUWU_ABORT_ON_FIRST_ERROR`, `SUSUWU_ECHO_COMMANDS_TO`, `SUSUWU_S`, `SUSUWU_SH_CONSOLE_PARAMS`, `SUSUWU_SH_<color>`, `SUSUWU_VERBOSE`}
- [`./sh/Transcode.sh`](./sh/Transcode.sh) is a standalone [`ffmpeg`](https://github.com/FFmpeg/FFmpeg)-based tool which goes with [`./posts/TranscodeMuxHowto.md`](./posts/TranscodeMuxHowto.md).

[`./hooks/`](./hooks/) is `git` scripts ([`man githooks`](https://git-scm.com/docs/githooks)) which assist you; install with `cp -ra ./hooks/* ./.git/hooks/`.
- [`./hooks/pre-commit`](./pre-commit) is [custom `pre-commit`](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) [`.git/hooks/pre-commit.sample` (scans for non-ASCII filenames, conflict markers or whitespace errors)](https://github.com/auth0/gitzero/blob/master/tests/example/_git/hooks/pre-commit.sample)

# How to use this
If `git` is not installed, browse [`./mid/`](./mid/) and click on individual `*.mid` samples to have the browser download those.
## Download
Download with `git clone https://github.com/SwuduSusuwu/SusuMid.git` and browse local with `cd mid/ && ls`.
- If this does not have all the samples you want, browse the ["beta test" / `preview` branch](#beta-test--preview-branch).
## Signatures / certificates
[`./.ssh/setup.sh`](./setup.sh) is to setup `gpg.ssh.allowedSignersFile` (allows to use `git verify <ref>` or `git log --show-signature`).
- `git verify <ref>` or `git log —show-signatures` shall match [`./.ssh/sha256.sig`](./.ssh/sha256.sig) for [new commits](https://github.com/SwuduSusuwu/SusuMid/blob/preview/SECURITY.md#user-content-fn-6-54b7777c7a2a5f42db6ee70c71bfec2e)
- You can compare those certificates to [this post](https://swudususuwu.substack.com/p/s256_1ywl0ridf6zuex1qazgx1ihgdytfkyf9t97gonfroio).)

\[Notice: This [public crypto](https://docs.gitlab.com/ee/user/project/repository/signed_commits/ssh.html#verify-commits-locally) "signature", is not related to "signature analysis" ([Substr scans](https://github.com/SwuduSusuwu/SusuLib/README.md#purposes)).\]

