# Staging trust configuration (public)

| File | Purpose |
|---|---|
| `root/root.json`, `root/root.json.sig` | Trust root, signed by the offline staging root key. Lists the online index key. |
| `root.pub` | The staging root public key. Clients embed it; `publish.yml` verifies against it. |
| `ledger-bootstrap.signers` | The trusted bootstrap for the moderation ledger (allowed-signers format). |
| `references.json.enc` | The private reference set, AES-256-GCM encrypted. Its key exists only as the `REFERENCES_KEY` secret. |

Nothing in this folder is secret. All private keys stay offline or in protected GitHub environment secrets.
