# Updating a project

- **New version:** change the version in `mod/mod.json` (or your modpack's pins), commit, tag `vX.Y.Z` and push the
  tag. Each release is checked and reviewed on its own. Players see the update once it is approved; their settings are
  kept, and they can return to the previous approved release.
- **Fixing a release:** releases are never edited after approval. Publish a new version.
- **Changing the licence:** update `project.license.name` and `LICENSE` together. The next release is checked against
  the new licence.
- **Renaming the repository:** fine. The project id and its history stay with the repository.
- **Transferring the repository:** its releases are held until a moderator reviews the transfer.
- **Modpacks:** to move members to newer approved releases, update the pins, run `python3 .admg/package.py sync`, then
  commit and release a new version. If a member is revoked, installed copies of your pack need that update.
- **Revocations:** if a problem is found in an approved release, ADMG Exchange can revoke it. Players are then warned,
  or the release is switched off, or the game won't start with it, depending on the severity. The public reason is
  shown on the project page. Release a fixed version, or appeal.
