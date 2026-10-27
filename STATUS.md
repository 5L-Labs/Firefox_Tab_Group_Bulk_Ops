# Status (parked 2026-10-27)

Read this first when resuming. Release steps live in [PUBLISHING.md](PUBLISHING.md).

## Where things stand

- `master` is clean and pushed; no open PRs.
- **Published:** version `1.0.3` is public on AMO as
  [tab-group-bulk-operations](https://addons.mozilla.org/en-US/firefox/addon/tab-group-bulk-operations/),
  add-on ID `group-same-site-tabs@njl.dev`. GitHub release `v1.0.3` is the latest; two stale
  `v1.0.3` **draft** releases from CI retries can be deleted.
- Release CI (`.github/workflows/release.yml`) reads the AMO secrets from the GitHub environment
  `AMO_API_KEY`. The same Mozilla account and API keys also publish
  [videospeed-firefox](https://github.com/NickJLange/videospeed-firefox) (see its `STATUS.md`);
  rotating the keys breaks both release jobs.

## Parked work

- **Alphabetical group sorting:** [PR #3](https://github.com/NickJLange/Firefox_Tab_Group_Bulk_Ops/pull/3)
  was closed unmerged. Branch `feature/alphabetical-sorting` still exists, but it predates the
  Mozilla-compliance and copy-group-URLs work, so rebase or re-implement on current `master`.
- Branch `mozilla-compliance` is fully merged (PR #4) and can be deleted.

## Resuming

- Load as a temporary add-on via `about:debugging`, or `web-ext run`. Lint with `web-ext lint`.
- Next version must be > `1.0.3`. Bump `manifest.json`, tag `vX.Y.Z`, push (see PUBLISHING.md).
- The `tabGroups` API is Firefox-specific; re-check its status in current Firefox before new work.
