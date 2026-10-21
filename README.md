# ADMG Exchange — staging index

This repository runs the **staging** pipeline of ADMG Exchange and serves the signed staging index. It holds metadata
only: no mods, packages or binaries are uploaded here. Software stays in each publisher's own public GitHub repository
and its releases.

**Signed index:**
- GitHub Pages: `https://admg-101.github.io/admg-exchange-index-staging/index/v1/index.json`
- Raw mirror (the same signed bytes): `https://raw.githubusercontent.com/ADMG-101/admg-exchange-index-staging/gh-pages/index/v1/index.json`

**Publishing.** Start from the ADMG Exchange mod or modpack template (or add the Exchange files to an existing public
repository), install the **ADMG Exchange Staging** GitHub App on the repository, and tag a release. The ADMG-101
launcher's Creator Hub guides you through the same steps. Discovery registers the repository and picks up each tagged
release; every release is published only after a human moderator approves its exact package. Projects need a public
repository; no licence is required.

Publisher guide: [publishing](docs/publishing.md), [the GitHub App](docs/github-app.md),
[troubleshooting](docs/troubleshooting.md), [updating](docs/updating.md), [appeals](docs/appeals.md).

| Path | What it is |
|---|---|
| `registrations/` | Registered projects (created by discovery) |
| `config/` | Public trust configuration: trust root, ledger bootstrap, encrypted reference set |
| `.github/workflows/` | `discover`, `validate`, `scan`, `publish`, `health` |
| `docs/` | The publisher guide |
| `.github/ISSUE_TEMPLATE/` | The appeal form |
| `gh-pages` branch | The published, signed index |
| `state` branch | Discovery state and onboarding status (`status.json`), plus health results |

This is a staging environment: its keys are disposable and its index is for testing only.
