# WFLY-18548 Support Matrix POC (staging)

This repository holds the patch intended for [`Joseluiscruz-hub/wildfly.org`](https://github.com/Joseluiscruz-hub/wildfly.org) (fork of `wildfly/wildfly.org`).

**Blocker:** the fork is **archived (read-only)**, so GitHub MCP cannot create branches or open a PR against upstream from it.

## Patch contents

| Path | Purpose |
|------|---------|
| `src/main/java/org/wildfly/site/model/Releases.java` | Filter WildFly 37+ via `supportMatrix()`; optional `java_se` mapping |
| `content/support-matrix.qute.json` | Qute template → `/support-matrix.json` |

## Design notes

- JSON generated from existing `data/releases.yaml` via Qute/Roq (no new plugin, no separate artifact).
- `java_se` is **null** unless present in release YAML — **no invented** Java SE compatibility values.
- Vocabulary for future YAML: `java_se.recommended` (string), `java_se.supported` (list of SE version strings), matching release-announcement language.

## After unarchiving the fork

1. Unarchive https://github.com/Joseluiscruz-hub/wildfly.org
2. Create branch `WFLY-18548-support-matrix-poc` from `main`
3. Copy these two files into the fork and commit with WFLY-18548 + Signed-off-by
4. Open PR: `Joseluiscruz-hub:WFLY-18548-support-matrix-poc` → `wildfly/wildfly.org:main`
