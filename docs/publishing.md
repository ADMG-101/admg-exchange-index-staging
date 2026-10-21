# Publishing on ADMG Exchange

ADMG Exchange lists mods and modpacks for games on ADMG-101. Your project stays in your own public GitHub repository.
Exchange reads it through a read-only GitHub App, checks each release, and lists it after a moderator approves it.
You never upload files to Exchange and you never need a token.

## What Exchange accepts

- **Mods** for games on ADMG-101, and **modpacks** that pin approved mods. ROM hacks and server software are not
  Exchange categories.
- From a **public GitHub repository**, with publicly inspectable source.
- Under an **open-source licence**: `project.license.name` in `.admg/exchange.json` is its SPDX identifier (for example
  `MIT`, `Apache-2.0`, `GPL-3.0-or-later`, `MPL-2.0`, `CC-BY-4.0`), and the unmodified licence text is in the
  repository's `LICENSE` file, so GitHub recognises it at the tagged commit.
- Released by **your repository's own workflow** from the tagged commit, with GitHub build provenance. Packages with
  code must carry a build-provenance attestation from that workflow.
- **Your own work**: no game ROMs, ROM patches, or extracted game graphics, music or text.
- Every release is reviewed and **approved by a moderator** before it is published.

## Get started

**New project:** create a repository from the ADMG Exchange **mod template** or **modpack template**. On GitHub, choose
**Use this template**, then **Create a new repository**, and make it public. A setup workflow fills in your project id
and names on the first push. Then follow the template's README.

**Existing project:** add the Exchange files to your repository, as described in "Publish an existing repository"
(`ADOPTING.md` in the template collection).

## Publish

1. **Install the GitHub App** on the repository ([github-app.md](github-app.md)). You can do this on GitHub, or from
   the ADMG-101 launcher: **Exchange**, then **Creator Hub**, then **Submit Project**. The launcher signs you in with
   GitHub and opens the App's installation page with your repository selected.
2. **Tag a release:** set the version in `mod/mod.json`, commit, then `git tag v1.0.0` and `git push origin v1.0.0`.
   The release workflow builds the package, attests its provenance and publishes the GitHub release.
3. **Wait for discovery.** About every 30 minutes, Exchange registers newly installed repositories and picks up new
   releases. A new repository is registered first; its releases are considered from then on.
4. **Checks.** Each release's package is fetched by its SHA-256, compared with your tagged source and its provenance,
   and inspected (nothing in it is run). The results go to the reviewer.
5. **Review.** A moderator approves or rejects the exact package. Approved releases appear in ADMG Exchange, and
   players install them from the launcher.

## Track your submission

- **In the launcher:** the Creator Hub shows your registration, each release's stage and the reasons a release was
  held back, with links to your release workflow runs.
- **Onboarding status:** `status.json` on this repository's `state` branch lists every repository the App can see,
  its registration state, and the reasons for each release.

## Rules of the road

- A project id (`<your-github-name>.<project-name>`) is bound to your repository for good. Renaming the repository keeps
  it. Transferring the repository to another owner holds its releases until a moderator reviews the transfer.
- Each release is approved on its own. Re-uploading an asset with different bytes makes it a new submission.
- Approved releases can be revoked later, for example if a problem is found. Players are then warned, or the release
  is switched off; see [updating.md](updating.md).

More: [troubleshooting.md](troubleshooting.md), [updating.md](updating.md), [appeals.md](appeals.md).
