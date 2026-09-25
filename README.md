# homebrew-scoursh

Homebrew tap for [scoursh](https://github.com/abhi-sama/scoursh), an egress-restricted security scanner (SAST, SCA, IaC, DAST, AWS posture, container image and network scanning).

## Install

```sh
brew install abhi-sama/scoursh/scoursh
```

Then:

```sh
scoursh --help
scoursh paths          # where your config, state and reports live
```

The formula installs the release archive into `libexec` and exposes `bin/scoursh` through a wrapper that runs Homebrew's Bash, because scoursh needs bash 4.2 or newer and macOS ships 3.2.

Your configuration, scan state, reports and advisory data live outside Homebrew (XDG directories under your home), so `brew upgrade` never removes them.

OpenSSL, SQLite and Git are deliberately not dependencies. They enable optional capabilities, and scoursh reports their absence as a declared coverage reduction rather than failing.

## Verifying a release

Every release is built reproducibly and signed with GitHub artifact attestations:

```sh
gh attestation verify scoursh-<version>.tar.gz --repo abhi-sama/scoursh
```

## Maintaining this tap

`Formula/scoursh.rb` is **generated**. Its source of truth is `packaging/homebrew/scoursh.rb` in the scoursh repository; the release workflow renders it with the tagged version and the build job's own SHA-256, then opens a pull request here. Edit the template there, not the formula here.
