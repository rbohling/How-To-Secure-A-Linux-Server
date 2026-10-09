# Contributing

Help improve this guide with corrections, distribution-specific notes, clearer explanations, and verified examples.

## Report a documentation problem

[Open an issue in this repository](https://github.com/rbohling/How-To-Secure-A-Linux-Server/issues/new). Include the section, distribution/release, relevant package version, expected behavior, actual behavior, and a proposed correction if available. Remove passwords, private keys, tokens, and identifying infrastructure details from examples and logs.

## Submit a change

1. Fork this repository and create a focused branch.
2. Explain why the recommendation helps and when it does not apply.
3. Link to primary sources, such as distribution documentation or upstream manuals.
4. For commands that change configuration, include prerequisites, verification, and rollback or recovery guidance.
5. State the distribution and version actually tested. If a change has only been reviewed against documentation, say so.
6. Check relative links and update navigation when adding sections.
7. Open a pull request describing the change and its validation.

Prefer small, reviewable changes. Do not claim a distribution is supported, a command is tested, or a benchmark is satisfied without evidence. Avoid universal hardening scripts that change SSH, firewalls, or kernel parameters without accounting for the server's role.

## Attribution and license

The original guide is by [Anchal Nigam](https://github.com/imthenachoman). Preserve original attribution and relevant historical references. Contributions to this adaptation are shared under the existing [Creative Commons Attribution-ShareAlike 4.0 license](LICENSE.txt).
