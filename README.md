# ADMG Exchange — staging index

This repository runs the **staging** pipeline of ADMG Exchange and serves the signed staging index. It holds metadata
only: no mods, packages or binaries are uploaded here. Software stays in each publisher's own public GitHub repository
and its releases.

**Signed index:**
- GitHub Pages: `https://admg-101.github.io/admg-exchange-index-staging/index/v1/index.json`
- Raw mirror (the same signed bytes): `https://raw.githubusercontent.com/ADMG-101/admg-exchange-index-staging/gh-pages/index/v1/index.json`

**Taking part as a publisher.** Install the **ADMG Exchange Staging** GitHub App on a public repository that contains
`.admg/exchange.json`. The ADMG-101 launcher's Creator Hub will guide you through the same step. Discovery finds the
installation, proposes a registration, and scans each tagged release. Every release is published only after a human
moderator approves its exact artifact.

| Path | What it is |
|---|---|
| `registrations/` | Registered projects (created by discovery) |
| `config/` | Public trust configuration: trust root, ledger bootstrap, encrypted reference set |
| `.github/workflows/` | `discover`, `validate`, `scan`, `publish`, `health` |
| `gh-pages` branch | The published, signed index |
| `state` branch | Discovery state and onboarding status (`status.json`), plus health results |

This is a staging environment: its keys are disposable and its index is for testing only.
