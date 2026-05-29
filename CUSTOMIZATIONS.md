# Customizations

Personal fork of [CloakHQ/CloakBrowser](https://github.com/CloakHQ/CloakBrowser) — tracking upstream, not contributing back. My changes live on the `mattb/main` branch; `main` stays clean for upstream syncs.

## Changes

_Add entries as you go — date, file, what & why._

- _YYYY-MM-DD_ — `path/to/file` — what changed and why

## Syncing upstream

```bash
git fetch upstream
git checkout main && git merge --ff-only upstream/main && git push origin main
git checkout mattb/main && git merge main  # resolve conflicts against your customizations
```

Or use GitHub's **Sync fork** button on the repo page (works only when `main` has no local divergence — keep `main` clean by working on `mattb/main`).

## License reminder

Upstream license: **MIT** — Permissive — adapt freely. Attribution required if you redistribute.

Note: The compiled Chromium **binary** ships under a separate `BINARY-LICENSE.md` (custom CloakHQ license). Personal and internal commercial use is fine; redistribution and SaaS wrapping require an OEM license from CloakHQ.

## Vetting conditions

Security vetting verdict was CONDITIONAL. Accepted 2026-05-29.

- **Binary license ≠ MIT** — wrapper is MIT; compiled binary is CloakHQ's custom BINARY-LICENSE. No redistribution, no third-party service use without OEM license.
- **ToS exposure** — bypassing Cloudflare, reCAPTCHA, etc. may violate ToS of targeted sites. Only use against sites you own or have written authorization to test.
- **Auto-update on by default** — background thread silently pulls new Chromium binaries from CloakHQ's CDN hourly. Set `CLOAKBROWSER_AUTO_UPDATE=false` to disable.
- **Young org** — CloakHQ created Feb 2026; upstream continuity dependent on ~2 primary contributors.
- **Proprietary binary** — trusting CloakHQ's build pipeline for ~200MB Chromium binary. SHA-256 verification is in place; disable auto-update and pin versions for production use.
