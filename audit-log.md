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

6. **Merge result:** PR #1 **merged** into `main` at 2026-10-21T15:17:23Z (merge commit `bcba4163f124a435c3af9200b935d8aad39b37bd`, merge method: merge). The PR is now closed with `merged: true`; the default branch contains both documentation files.

7. **Secret scanning result:** **inconclusive — blocked by permissions, not clean and not dirty.** The token used for this walkthrough lacks access to secret scanning data. No alerts could be listed and none could be pulled for detail. This must be re-run by someone with security-events read access before sign-off.

8. **Overall verdict:** **Workflow verified end to end; one open gap.**
   - ✅ Repository, branch, two-file documentation commit, pull request, running log, diff review, and merge all functioned exactly as intended — the process itself is sound and repeatable for the team.
   - ✅ The diff review accounted for every changed file and line count, with no surprises.
   - ⚠️ The secret scanning sweep did not complete due to the token's permissions. Until it is re-run with proper access, the audit cannot be signed off as clean. Per the team checklist, this is item #5 and #6 — both currently **not** signable.
   - **Recommendation:** the team lead or security reviewer should (1) confirm secret scanning is enabled for this repository, (2) run the alert sweep with appropriate credentials, and (3) then complete checklist items 5–6. Everything else is ready for Thursday.
