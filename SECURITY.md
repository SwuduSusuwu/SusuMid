# Security Policy
All [commit signatures](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits) shall match [`./.ssh/sha256.sig`](./.ssh/sha256.sig) values. [./README.md#signaturecertificate](./README.md#signaturecertificate) shows how to test this on your own.

[`./.ssh/allowed_signers.old`](./.ssh/allowed_signers.old) holds [old certificates](#erratafootnotes) (not known as "compromised"; just no longer used). **TODO**; warn if new commits use old certificates.
## Supported versions
Users can expect that [`trunk`](https://github.com/SwuduSusuwu/SusuMid) passes [_GitHub_'s code scans](https://github.com/SwuduSusuwu/SusuMid/security/code-scanning?query=branch%3Atrunk+tool%3ACodeQL) and [_Codacy_'s code scans](https://github.com/SwuduSusuwu/SusuMid/security/code-scanning?query=branch%3Atrunk+tool%3A%22Cppcheck+%28reported+by+Codacy%29%22%2C%22Shellcheck+%28reported+by+Codacy%29%22%2C%22Flawfinder+%28reported+by+Codacy%29%22%2C%22Jacksonlinter+%28reported+by+Codacy%29%22%2C%22Remark-lint+%28reported+by+Codacy%29%22)

## Sensitive issues
First, view [How to contribute](./README.md#how-to-contribute) for information on issues (to ensure that what you found is not a normal issue).

If you found [normal issue(s), such as this](https://github.com/SwuduSusuwu/SusuLib/security/code-scanning/1882), use [this normal route to post about new issues](https://github.com/SwuduSusuwu/SusuMid/issues/new).

But if you found [sensitive issue(s), such as this](https://github.com/SwuduSusuwu/SusuMid/security/code-scanning/1277), you have a few options to report the issue:
- through a [new private advisory](https://github.com/SwuduSusuwu/SusuMid/security/advisories/new),
- through private message to <https://github.com/SwuduSusuwu> (if _GitHub_ now allows private messages),
- or <mailto:2002swudususuwu@gmail.com>.
- If there is no response soon, you can also contact <https://substack.com/@swudususuwu>.

You can expect:
- Best effort to address the issue(s),
- with you anonymous (unless you ask to publish credits to you.)

## Errata/footnotes
This section is for notices such as: revoked (or deprecated) certificates.

