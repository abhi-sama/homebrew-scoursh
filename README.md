# homebrew-scoursh

Homebrew tap for [scoursh](https://github.com/abhi-sama/scoursh), an egress-restricted shell security scanner (SAST, SCA, IaC, DAST, AWS posture, container image and network scanning).

## Status

**No formula is published yet.** `Formula/scoursh.rb` lands with scoursh's first tagged release (`v1.0.0`), when the release job renders the formula template with that release's version and its build-job SHA-256.

Until then, install from source:

```sh
git clone https://github.com/abhi-sama/scoursh
cd scoursh && ./scan.sh --help
```

## Once the formula is published

```sh
brew install abhi-sama/scoursh/scoursh
```

The formula installs the release archive into `libexec` and exposes `bin/scoursh` through a wrapper that runs Homebrew's Bash rather than macOS's Bash 3.2. OpenSSL, SQLite and Git are deliberately not dependencies: they enable optional scanner capabilities, and scoursh reports their absence as a declared coverage reduction rather than failing.

The formula source of truth is `packaging/homebrew/scoursh.rb` in the scoursh repository; changes belong there, not here.
