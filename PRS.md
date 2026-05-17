# SixFive7/Erugo — PR tracker

This fork hosts four in-flight PRs against [ErugoOSS/Erugo](https://github.com/ErugoOSS/Erugo). Each PR has its own branch in this fork and a dedicated worktree on disk for parallel work.

| # | Branch | Worktree | PR | Status |
|---|--------|----------|----|--------|
| 1 | `feat/i18n-nl-quality` | `C:\Source\SixFive7\Erugo-pr-i18n` | [#235](https://github.com/ErugoOSS/Erugo/pull/235) | in review |
| 2 | `feat/users-form-autocomplete` | `C:\Source\SixFive7\Erugo-pr-autocomplete` | [#236](https://github.com/ErugoOSS/Erugo/pull/236) | in review |
| 3 | `feat/auth-auto-redirect-single-sso` | `C:\Source\SixFive7\Erugo-pr-oidc` | [#237](https://github.com/ErugoOSS/Erugo/pull/237) | in review |
| 4 | `feat/docker-shares-path-env` | `C:\Source\SixFive7\Erugo-pr-shares` | [#234](https://github.com/ErugoOSS/Erugo/pull/234) | in review |

## Scope per PR

1. **i18n-nl-quality** — Improve Dutch translation quality and add missing keys in `resources/js/i18n/nl.json`, comparing against the English source.
2. **users-form-autocomplete** — Add `autocomplete` / password-manager-ignore attributes to the add and edit user inputs in `resources/js/components/settings/users.vue`, mirroring upstream commit `e7bdddf` ("Enhance SMTP settings form to prevent browser autofill").
3. **auth-auto-redirect-single-sso** — Add admin settings to auto-redirect `/login` to a single configured SSO provider, with a `?manual=1` URL-param escape hatch. Touches `resources/js/components/auth.vue`, the settings UI/backend, and likely a migration.
4. **docker-shares-path-env** — Add an `ERUGO_SHARES_PATH` env var to `docker/alpine/start-container` so uploaded shares can live on a separate volume from the SQLite DB and application data.

## Conventions

- **Base**: every PR branch was created from `upstream/main` and must be rebased against `upstream/main` (not `origin/main`) before opening the PR.
- **Tracker file**: `PRS.md` lives only on `origin/main` of the fork. It must never appear in a PR branch. If a worktree shows `PRS.md` in its working tree, that branch was created from the wrong base — recreate it.
- **Commit style**: short imperative, sentence case, no scope prefix, no trailing period. Mirror recent upstream commits like `Fixes RCE in uploads controllers`, `Enhance SMTP settings form to prevent browser autofill`, `Add translations for new share-related messages and interrupted upload notifications`.
- **PR target**: `ErugoOSS/Erugo:main` from `SixFive7:<branch>`. Command: `gh pr create --repo ErugoOSS/Erugo --base main --head SixFive7:<branch> --title "..." --body-file <file>`.

## Status updates

Update the table above when a PR opens (replace `_not opened_` with the PR URL), changes state (`branch ready` → `in review` → `merged`), or is closed.
