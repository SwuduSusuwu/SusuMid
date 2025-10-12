(C) 2024 Swudu Susuwu, dual licenses: choose [_GPLv2_](./LICENSE_GPLv2) or [_Apache 2_](./LICENSE) (allows all uses).

# Table of Contents
- [Purposes](#purposes)
- [How to use this](#how-to-use-this)
  - [Download](#download)
  - [Signatures / certificates](#signatures--certificates)
- [How to contribute](#how-to-contribute)
  - [Beta tests / `preview` branch](#beta-tests--preview-branch)
  - [Good first issues to contribute to](https://github.com/SwuduSusuwu/SusuMid/contribute)
  - [Contributor conventions / rules](#contributor-conventions--rules)
    - [_Markdown_](#markdown)
    - [`git`](#git)
    - [`sh` source](#sh-source)
  - [Sponsor](#sponsor)
    - [Escrow](#escrow)
    - [Affiliates](#affiliates)

# Purposes
[`./.ssh/`](./.ssh/) is to [use signatures / certificates](#signatures--certificates).

[`./mid/`](./mid/) stages [`.mid`](https://wikipedia.org/wiki/MIDI#Computer_files) sound (music) samples for <https://swudususuwu.substack.com/podcast> and [SwuduSusuwu on Youtube](https://www.youtube.com/watch?v=jbyE0W4FFjA&list=PLTYe2PlBb7aeNRwaNvbvpqFsoCa5S6fyx&index=2).
- Much of those were not stored as `.mid`, and the few that were sound best if opened with [_Perfect Piano_](https://play.google.com/store/apps/details?id=com.gamestar.perfectpiano&hl=en-US) with the instrument from the filename.
- The filenames are formatted as `YY-MM-DD_HHMM[SS]_Instrument_[Title].mid`.

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

# How to contribute
View [documented issues](https://github.com/SwuduSusuwu/SusuMid/issues/) (for ideas on what to contribute, plus so you do not report documented issues.)
## Beta tests / [`preview`](https://github.com/SwuduSusuwu/SusuMid/tree/preview/) branch
- Opt-in with `git switch preview` (opt-out with `git switch trunk`).
  - Preview [samples](https://github.com/SwuduSusuwu/SusuMid/tree/preview/mid/) / [scripts](https://github.com/SwuduSusuwu/SusuMid/tree/preview/sh/) for symptoms of new issues (hint: listen to samples for glitches, or look through script outputs for "Warning:"s or "Error:"s).
  - If you found new issue(s) (which aren't due to misconfigurations in your system), [post new issue(s)](https://github.com/SwuduSusuwu/SusuMid/issues/new).
    - Notice: [sensitive issue(s)](./SECURITY.md#sensitive-issues) have a separate protocol.

# Contributor conventions / rules
General comment/message syntax rules: `<>` goes around type of option/argument (such as `<commit-hash>`, `[]` goes around optional comments/options/arguments (such as `[<optional fallback value>]`, `...` is affixed to allow multiple options/arguments (such as `[; optional extra arguments]...`). This rule is used to document function arguments (such as `sh`, `C` or `C++` use), plus to document `git` uses.
To ensure consistent code, submissions of code (such as through [pull requests](https://github.com/SwuduSusuwu/SusuMid/pulls)) have language-specific syntax rules:
## _Markdown_
`` *.md `` shall use:
- [_GitHub flavored Markdown_](https://github.github.com/gfm/), which is not just compatible with [_GitHub_](https://github.com) but also:
  - Has lots of [unit tests](https://wikipedia.org/wiki/Unit_test#Agile). Most of the differences from the original _Markdown_ are just so rules are less ambiguous.
  - Is close to the original _Markdown_ (thus compatible with most _Markdown_ tools, such as [`glow`](https://github.com/charmbracelet/glow?tab=readme-ov-file#glow)).
- [_ISO 8601_](https://wikipedia.org/wiki/ISO_8601), which
  - Is the most popular national standard format.
  - Versus formats which use locale-dependent names of months, is more portable and less ambiguous.
  - Versus formats which use backslashes, is more portable (filesystem paths can include).
- [_Unix_](https://wikipedia.org/wiki/Unix) paths start with `./` (if relative) or `/` (if absolute), so that [`sed`](https://manpages.org/sed) (and [`grep`](https://manpages.org/grep)) [performance is improved](https://poe.com/s/NX7kVKtCL9k04WIqieoh).
  - That is, paths shall match the [Regular Expression](https://wikipedia.org/wiki/Regular_expression) `^\.*\/[\w]*` (more than 1 `.` is allowed).
  - [_Microsoft Windows_](https://wikipedia.org/wiki/Microsoft_Windows) can use _Unix_ paths, except that absolute paths must start with the drive prefix (`[A-Z]:/` versus `/`).
  - [_HTTP_](https://wikipedia.org/wiki/HTTP) can use _Unix_ paths, except that absolute paths must start with the protocol (`http[s]*://` versus `/`).
## `git`
If `git commit` introduces/removes functions, have `./README.md#purposes` include this.
Do atomic commits: if swapping the new commit with a previous commit (such as through `git rebase -i`) -- or if `git revert` of a previous commit -- causes  `./build.sh` to return a non-0 exit status, `git commit`'s message shall include such as:
> Is followup to: \<ref | commit-hash\> \(\<commit-message\>\)\[, comment\] \[; \<ref | commit-hash\> \(\<commit-message\>\)\[, comment\]\]...

- This shows the temporal order of commits required for `./build.sh` to pass.
- `<commit-message>` is so that `git rebase` (which changes `<commit-hash>`) does not make it impossible to follow (plus, so comments are reduced), thus you should use the exact message. You can use ellipsis (`...`) to omit extra lines, but it is best if the first line is exact (left as-is).
- Notice: [commit 9eda0ed5ed2abcdcec92c5b265f6e950e1196558 (+`sh/Macros.sh:SUSUWU_SH_{FILE, LINE, FUNC}`)](https://github.com/SwuduSusuwu/SusuLib/commit/9eda0ed5ed2abcdcec92c5b265f6e950e1196558/), and older, used `,` (as opposed to `;`) to delimit the list of commits; those extra `<ref | commit-hash>`'s are not extra comments, but are extra commits. The new format allows comments to include `<commit-hash>`'s and `,`'s (just not `;`'s).

`git commit` message format/syntax:
- affix "()" onto functions (regardless of number of arguments), such as `function()`, or use the function name (such as `function`) alone.
- if commit does `git add NewFile`: message has `+\`NewFile\``.
- if `git rm Exists`: `-\`Exists\``.
- if `touch Exists && git add Exists`: `@\`Exists\`` or `?\`Exists\``.
  - Simple wildcards/regex for altered functions: `\`%s/oldFunction()/newFunction()/\``.
  - '*' is not used as update prefix, since '*' has much other use in _Regex_ (wildcards) & _C++_ (such as block comments, dereferences, or math).
    - From the root commit through 159940fb8b60b176a38a13cdfbd9393596daa9b5 (Date:   Thu Jul 4 07:56:01 2024 -0700), '@' was the prefix for updates. From then until this commit, '?' was the prefix for updates.
    - From this commit on (this is the successor to commit 0ae6233c02d9e04fca60027b1e32b885eb69bb8a (Date:   Sat Nov 30 17:50:40 2024 -0800)), '@' is (once more) the prefix for updates, due to: it is more common for projects to so use '@'.
- if `echo "int newFunction() {...}" >> Exists && git add Exists`: `@\`Exists\`:+\`NewFunction()\``.
- if `git mv OldPath/ NewPath/`: `\`OldPath/\` -> \`NewPath/\`` or `mv OldPath/ NewPath/`.
- as default branch, choose `master`, `main` or `trunk` (do not have more than 1 of those branches, or [`./Macros.sh:SUSUWU_DEFAULT_BRANCH()`](./Macros.sh) is ambiguous).
- to indent: use tabs to form blocks, such as:
```
?`README.md`:
	?`#How-to-use-this`:
	Split into:
		+`## Download`: new; howto clone, howto switch branches.
		+`## Optionssetup`: "Options/setup"; howto use `./build.sh` (with or without options.)
	?`#How-to-contribute`,
	?[Good first issues to contribute to]: (moved into `#How-to-contribute`)
```
/[Notice: Commit titles can omit backticks (``) if not enough room; the backticks just allow _GitHub_ to do _Markdown_-format code/paths.\]
## `sh` source
Is as for [_C_/_C++_ source](#cc-source), plus specifics to `sh`:
- Act as if all functions/variables are macros (which use `CONSTANT_CASE`).
- Variable access: uses `${...}` (thus not `echo $BOOL`, but `echo ${BOOL}`).
  - Rationales:
    - In case future versions append to this (`echo $BOOL2` is a silent error, but `echo ${BOOL}2` is cool).
    - Avoids [SC2250](https://www.shellcheck.net/wiki/SC2250) ["Prefer putting braces around variable references even when not strictly required." notices](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning?query=rule%3Ashellcheck_SC2250).
  - Exceptions: [**language limits**](https://www.shellcheck.net/wiki/SC3030).
    - To support `/bin/sh`: do not use `${@}`, but `$@`.
- Str variable access: uses `"$..."` (thus not `ls ${STR}`, but `ls "${STR}"`).
  - Rationales:
    - So if `STR="/bin/"` is replaced with `STR="/path with/spaces/"` ([without `IFS=""`](https://tldp.org/LDP/abs/html/internalvariables.html#IFSREF) \[[2](https://www.commandlinux.com/man-page/man1/sh.1.html#lbBK)\]), that 1 parameter [won't expand into 2](https://tldp.org/LDP/abs/html/special-chars.html#FIELDREF).
    - So if `STR="/bin/"` is replaced with `STR="*"` ([without `set -f`](https://www.commandlinux.com/man-page/man1/sh.1.html#lbBL)), the glob is passed to `ls` (which [expands this into numerous paths](https://tldp.org/LDP/abs/html/globbingref.html), rather than expanded in your script.
    - Avoids [SC2086](https://www.shellcheck.net/wiki/SC2086) ["Double quote to prevent globbing and word splitting." notices](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning?query=rule%3Ashellcheck_SC2086).
  - Exceptions: specifics of command use.
    - Do not use `ctags "${FLAGS}" "${PATH}"`, but `ctags ${FLAGS} "${PATH}"`.
- Str variable access: uses `"${...}"` (thus not `if [ "-q" = ${PARAM} ]`, but `if [ "-q" = "${PARAM}" ]`).
  - Rationales: in case `${PARAM}` has spaces.
    - Avoids [SC2068](https://www.shellcheck.net/wiki/SC2068) ["Double quote array expansions to avoid re-splitting elements." notices](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning?query=rule%3Ashellcheck_SC2068).
  - Exceptions: to split (on spaces) is the purpose of the `for` loop.
    - To parse numerous params: do not use `for VALUE in "$@"`; do`, but `for VALUE in $@; do`.
- Restrict temp variables:
  - Rationales: avoids [*shadowed variables*](https://wikipedia.org/wiki/Variable_shadowing) (such as `f2() { VALUE=false; }; f1() { VALUE=true; f2(); return VALUE; };` causes).
  - If your project will always stick to `/bin/bash` (if does not have to support _POSIX_ systems), you affix `local` (thus not `for VALUE in ${LIST}; do`, but `local VALUE; for VALUE in ${LIST}; do`) to do this.
    - Exceptions: [**language limits**](https://austingroupbugs.net/bug_view_page.php?bug_id=767).
      - `local` is [not applicable to `IFS="<delimiter>"` or `cd <path>`](https://unix.stackexchange.com/questions/493729/list-of-shells-that-support-local-keyword-for-defining-local-variables/493838#493838), [not applicable to `readonly`](https://unix.stackexchange.com/questions/506009/unable-to-have-a-local-variable-with-the-same-name-as-a-global-read-only-variabl) (so use **subshells** for this).
      - If you require code which is consistant across platforms ([`local` has inconsistant dynamic versus static scope, plus inconsistant inheritance](https://unix.stackexchange.com/questions/493729/list-of-shells-that-support-local-keyword-for-defining-local-variables/493743#493743)), use **subshells** for this.
  - If your project supports _POSIX_ (`/bin/sh`): do not use `local` (such as `f2() { local VALUE=false; }`), but [use **subshells** for this](https://stackoverflow.com/questions/18597697/posix-compliant-way-to-scope-variables-to-a-function-in-a-shell-script/64946874#64946874) (such as `f2() ( VALUE=false; )`.)
    - Rationales (other than `local`'s **language limits**):
      - Avoids [SC3034](https://www.shellcheck.net/wiki/SC3043) ["In POSIX sh, local is undefined." notices](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning?query=rule%3Ashellcheck_SC3043).
- Command variables: uses `$(...)` (thus not `` stat `pwd` `` , but `stat $(pwd)`).
  - Rationales:
    - Most simple to nest (`echo $(stat $(pwd))`). Common (much known) **subshell** syntax is reused.
    - Avoids [SC2006](https://www.shellcheck.net/wiki/SC2006) ["Use $(...) notation instead of legacy backticked ...." notices](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning?query=rule%3Ashellcheck_SC2006).
## _C_/_C++_ source
Linter: `apt install clang && clang-tidy cxx/*.cxx` (defaults to [`.clang-tidy`](./.clang-tidy) options).

Most of what [_Mozilla Org_'s (_Firefox_'s) style](https://firefox-source-docs.mozilla.org/code-quality/coding-style/coding_style_cpp.html) suggests is sound (you should follow this unless you have specific reasons not to).

Code rules (lots overlap with _Mozilla Org_'s):

- Indent: tabs ('^I'); as much tabs as braces ('{' = +1 tab, '}' = -1 tab). \[All which conflicts with _Mozilla Org_'s format is tab use.\]
  - Rationales: reduced memory use, allows local configs (such as `~/.vimrc`) to set width, allows arrow keys to move fast.

- Files: `${C_SOURCE_PATH}/PascalCase.*` or `${CXX_SOURCE_PATH}/PascalCase.*xx` (such as: `./cxx/ClassFoo.hxx`, used as `#include "ClassFoo.hxx" /* classFooFunction() */`), as this is most common.
  - `./build.sh` requires: that all local includes prefix as `Class*.hxx` (so it knows to execute `--rebuild` if you upgrade a common include.) TODO: incremental builds which don't require this.
  - To assist with insertion/removal of `#include` statements, comments shall list all functions/macros used.

- Structs, enums, classe: `typedef struct PascalCase {} PascalCase;`, `typedef enum PascalCase {} PascalCase;`, `typedef class PascalCase {} PascalCase;`, as this is most common.

- Macros: `#define NAMESPACE_CONSTANT_CASE(snake_case_param) assert(snake_case_param);`, as this is most common.
  - [Indent multi-level macros as `#if X # if S ,,, # endif #endif`](https://stackoverflow.com/questions/1854550/c-macro-define-indentation).
  - [\_DEBUG is specific to MSVC, thus use NDEBUG](https://stackoverflow.com/questions/2290509/debug-vs-ndebug), [Pass `-D NDEBUG` to disable asssets + enable optimizations](https://stackoverflow.com/questions/2249282/c-c-portable-way-to-detect-debug-release).
  - Do not perform tasks within `assert()`, due to: the standard says "\[`#if NDEBUG\n#define assert(x) (0)\n#endif`\]".

- Braces, functions:
  - Do not produce lots of functions with the same name but different arguments, as such "overloads" make this difficult to [port](https://github.com/SwuduSusuwu/SusuLib/issues/10).
  - Single statement blocks can use the form: `virtual bool hasInstance() { return true; }`.
  - Most common form:
    ```c++
    /* const prevents `if(func() = x)` where you wished for `if(func() == x)` */
    const bool classPrefixCamelCase(bool s, bool x) {
    	if(s && x) {
    		return s;
    	} else {
    		return x;
    	}
    }
    ```
- Args/params, local variables, objects: `const bool camelCase = true`; Global variables/objects: `extern const bool classFooFunction;`, as this is most common.
  - Functions/globals can omit "classFoo" if wrapped as `namespace ClassFoo { extern bool global; };`, or (for `class ClassFoo { static bool global; };`).
    - The project as a whole should have `namespace Susuwu {};`, but you can nest `namespace`s.)
- For error, warning or notice syntax use: `"[WARN_LEVEL: OPTIONAL_FUNCTION_NAME {code which triggered the error/warning/diagnostic/notice} /* OPTIONAL COMMENTS */]"`,
  - [`./cxx/Macros.hxx`](./cxx/Macros.hxx): {SUSUWU_STR(x), SUSUWU_CERR(x), SUSUWU_STDOUT(x)} have the new syntax for this.
  - Modules should choose one of this list to send all userland errors, warnings or notices to:
    - `throw std::runtime_error(message)` (or `throw Q()` where `class Q : public std::exception`)
    - `std::cerr << message` (or `fprintf(stdout, message)`
    - `errno = code;`, or `return code;`.
- Follow tools such as {`clang++`, `g++`, `vim`, _Markdown_}:
  - use [`./cxx/Macros.hxx`](./cxx/Macros.hxx)`:SUSUWU_SH_BROWN` (and / or `` `<code>` ``) to quote code (or commands).
  - use `./cxx/Macros.hxx:SUSUWU_SH_PURPLE` (and / or `"<path>"`) to quote paths.
  - use `./cxx/Macros.hxx:SUSUWU_SH_LIGHT_CYAN` to quote names of functions.
  - use `./cxx/Macros.hxx:SUSUWU_SH_RED` to quote error messages.
  - use `./cxx/Macros.hxx:SUSUWU_SH_PURPLE` to quote status codes (or return values).
  - use `./cxx/Macros.hxx:SUSUWU_SH_LIGHT_CYAN` to quote names of variables / constants.
  - use `./cxx/Macros.hxx:SUSUWU_SH_GREEN` to quote (current) arguments / values.
  - use `./cxx/Macros.hxx:SUSUWU_SH_LIGHT_PURPLE` to quote (speculative / proposed) replacement arguments / values.
  - [`.sh`](#sh-source) code uses `./sh/Macros.sh:SUSUWU_SH_<color>`; new values above should also goto [`./sh/Macros.sh`](./sh/Macros.sh).

- Comments
  - Comments about possible `return code;`s (or `throw`s) go above function declarations (_Doxygen_ convention).
    - It is arguable whether or not you should document all possible system errors; most _Standard Template Library_ functions can `throw`.
  - `*.hxx` is to document interfaces (above function declarations); `*.cxx` is to do implementations (do not duplicate interface comments).
  - Use _Markdown_. Rationales: for non-English users (or for computers), such syntax assists use.
  - Instead of `//new single-line comments`, prefer `/* old fashioned */`.
    - Rationale: simpler to port. More obvious where the comment stops if the comment wraps around.
  - [_Doxygen_-ish "@pre"/"@post" prepares for _C++26_ _Contracts_](https://github.com/doxygen/doxygen/issues/6702):
    ```c++
    /* @throw std::bad_alloc If function uses {`malloc`, `realloc`, `new[]`, `std::*::{push_back, push_front, insert}`}
     * @throw std::logic_error Optional. Would include most functions which use `std::*`
     * @pre @code !output.full() @endcode
     * @post @code !output.empty() @endcode
     */
    bool functionDeclaration(std::string input, std::deque<vector> output);
    ```
    - As soon as `clang++` (or `g++`) has _Contracts_ (part of _C++26_), regular expressions (such as `:%s/@pre (.*) @code (.*) @endcode/[[expects: \2]] \\* \1 \\*/` `:%s/@post (.*) @code (.*) @endcode/[[ensures: \2]] \\* \1 \\*/`) can convert _Doxygen_-ish comments into contracts.
    - [`./cxx/Macros.hxx`](./cxx/Macros.hxx) has `SUSUWU_ASSUME(X)`, which is close to `[[expects: x]]`, but `SUSUWU_ASSUME(X)` goes to `*.cxx`, whereas `[[expects]]` goes to `*.hxx`.
    - Advantages of `[[expects]]`: allows to move information of interfaces out of `*.cxx`, to `*.hxx`.
- Include guards:
  ```c++
  #ifndef INCLUDES_Path_To_File
  #define INCLUDES_Path_To_File
  #endif /* ndef INCLUDES_Path_To_File */
  ```
## Sponsor
To sponsor this (which allows us to produce more source codes), you can use crypto (such as [**Bitcoin**](https://wikipedia.org/wiki/Bitcoin)) to [produce a one-time-use address](https://poe.com/s/IPhIMyuMY6SnYM0yqEJl) (which you deposit funds into), and send the address&private-key to [a contact which `./SECURITY.md` lists](./SECURITY.md#sensitive-issues).
- Rather than us publish a send-to address (for a particular protocol), this allows us to accept all forms of crypto.
- If amount is more than $100 and you don't trust the contact platforms, use [`./.ssh/id_ed25519.pub`](./.ssh/id_ed25519.pub) to [secure those](https://superuser.com/questions/576506/how-to-use-ssh-rsa-public-key-to-encrypt-a-text/1850928#1850928).
### Escrow
If you want proof that your crypto/cash will go to produce specific systems, use [**escrow** services](https://wikipedia.org/wiki/Escrow) (what you send the **escrow** is: crypto/cash, plus contract which references an [open issue which you choose](https://github.com/SwuduSusuwu/SusuMid/issues/)).
- If none of those issues match what you want, you can [post your own issue](https://github.com/SwuduSusuwu/SusuMid/issues/new) for this.
- Ensure that the **escrow** contract includes specifics as to what will count as "issue closed" [to the **escrow** service (so you do not have to trust the author),](https://wikipedia.org/wiki/Online_dispute_resolution) which will release the crypto/cash (once the **escrow** service considers your issue as closed).
  - For example; "The **source code** (through `./build.sh`), must produce a **system** (a **shared object** or **executable**) which uses just half of the training data to [setup its neural network, which must produce virtual synapses](https://wikipedia.org/wiki/Backpropagation) which the **system** [uses to produce **accurate** results](https://wikipedia.org/wiki/Residual_neural_network#Forward_propagation) on the other half, where **accurate** (for [classifiers](https://wikipedia.org/wiki/Learning_classifier_system)) is less than 2% false negatives and less than 2% false positives, and **accurate** (for [generators](https://wikipedia.org/wiki/Generative_artificial_intelligence)) is [divergence](https://wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence) of less than 2%." is a contract which an **escrow** can use for [issue #6](https://github.com/SwuduSusuwu/SusuLib/issues/6).
### Affiliates
You can use [_Capital 1_'s affiliate program](https://i.capitalone.com/JgR02Y4pE) to allow us to produce more source codes.

