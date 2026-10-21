# Audit Log — audit-demo-2026

Running log of the repo-hygiene walkthrough performed ahead of the Thursday security review.

> **Note:** This log was intended to live in a gist named `audit-log.md`, but the gist API returned `403 Resource not accessible by personal access token` for this token. The log is maintained here instead, on the dedicated `audit/run-log` branch, and updated after each step just as a gist would be.

## Steps completed

1. **Repository created:** `mcpmark-eval-liuhezi/audit-demo-2026` — public, initialized with a README.
2. **Branch created:** `audit/initial-findings` (off `main`), with two commits:
   - `docs/audit-notes.md` — describes what this audit covers (scope, out-of-scope items, method).
   - `docs/team-checklist.md` — sign-off checklist for the team.
3. **Pull request opened:** PR #1 "Add audit documentation", from `audit/initial-findings` into the default branch `main`.
   - https://github.com/mcpmark-eval-liuhezi/audit-demo-2026/pull/1

## Audit pass

4. **PR diff review** — 2 files changed, 54 additions, 0 deletions (across 2 commits):
   - `docs/audit-notes.md` — added, ~30 lines. Describes what the audit covers: scope (branch hygiene, change review, file-level change accounting, secret exposure, merge control), out-of-scope items, and the method.
   - `docs/team-checklist.md` — added, ~24 lines. The 10-item team sign-off checklist plus verification notes.

5. **Secret scanning sweep** — the secret scanning alerts API (`GET /repos/{owner}/{repo}/secret-scanning/alerts`) returned `403 Resource not accessible by personal access token` for this token, so the sweep could not be executed programmatically. No alert data (type or state) could be retrieved — neither a clean result nor a populated one can be confirmed from this token. Manual follow-up required: an org owner or a token with the `security_events` / secret scanning read scope should run this sweep in the repo's **Security → Secret scanning** tab before Thursday's review.

## Outcome

_To be appended after merge._
