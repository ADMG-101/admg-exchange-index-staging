# Release troubleshooting

When a repository or release is held back, Exchange says why in the launcher's Creator Hub and in `status.json` on this
repository's `state` branch. Common reasons:

| Message | What to do |
|---|---|
| `The project id must start with '<owner>.'` | The first part of `project.id` is your GitHub account or organisation name, in lowercase. |
| `'<id>' is already registered to another repository` | Project ids are unique; choose another name. |
| `Exchange lists only public repositories` or `The repository is archived` | Make the repository public, or unarchive it. |
| `Tag 'x' is not a semantic version` | Tag releases like `v1.2.3`. |
| `Declared asset '...' is not attached to the release` | The release workflow failed or was not used. Open the tag's **Actions** run and fix the error, then release again (see below). |
| `GitHub reports no SHA-256 digest for '...'` | The asset is still uploading, or was uploaded another way. Release through the workflow. |
| `The descriptor at v... describes '...'` | `.admg/exchange.json` at that tag has a different project id or type from the registered one. |
| `Draft releases are not considered` | Publish the release (the workflow does this for you). |
| `The repository was transferred; releases wait for a moderator` | Nothing to do: a moderator reviews the transfer. |

## The release workflow failed

Open **Actions**, then **release**, for your tag. The `package.py check` errors name the file and field to fix, and
you can run `python3 .admg/package.py check` locally. A version mismatch means the version in `mod/mod.json` differs
from the tag.

Fix the problem and commit. If no GitHub release was published for the tag, delete the tag
(`git push --delete origin v1.2.3`) and tag the fixed commit again. If a release was already published, use a new
version instead.

## Mods with code

The package needs a build-provenance attestation from this repository's release workflow; a DLL built elsewhere and
committed is not accepted. Set the repository variables `ADMG_SDK_KIT_URL` and `ADMG_SDK_KIT_SHA256` so the workflow
can build against the SDK reference kit.

## Held for review

Some findings, such as files the checks cannot match to your source, are decided by a moderator rather than
automatically. You may be asked for changes. If a release is rejected, you can fix it and release a new version, or
appeal ([appeals.md](appeals.md)).
