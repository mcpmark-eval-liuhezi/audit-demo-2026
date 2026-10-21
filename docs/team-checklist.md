# Team Sign-off Checklist — audit-demo-2026

Use this checklist during the Thursday security review. A line item is only considered signed off when the named owner has confirmed it and recorded the date. The audit is not complete until every item is checked.

## Sign-off checklist

| # | Item | Owner | Status | Signed off (date) |
|---|------|-------|--------|-------------------|
| 1 | Repository exists, is public, and is initialized with a README | Team lead | ☐ | — |
| 2 | Audit documentation is committed on a dedicated branch (`audit/initial-findings`), not directly on the default branch | Team lead | ☐ | — |
| 3 | Pull request opened from the audit branch into the default branch | Team lead | ☐ | — |
| 4 | PR diff reviewed: changed files identified and line counts recorded | Reviewer | ☐ | — |
| 5 | Secret scanning sweep completed and results recorded | Security reviewer | ☐ | — |
| 6 | Any secret scanning alerts investigated with full details (type, state) pulled | Security reviewer | ☐ | — |
| 7 | Running audit log (gist) maintained and kept up to date | Scribe | ☐ | — |
| 8 | Pull request merged into the default branch | Team lead | ☐ | — |
| 9 | Final outcome and verdict appended to the audit log | Scribe | ☐ | — |
| 10 | Audit log shared with the team | Team lead | ☐ | — |

## Verification notes

- The default branch must remain untouched by hand: all changes arrive via pull request.
- Secret scanning findings, if any, must be triaged before merge — an unresolved leaked credential blocks the merge.
- The audit log gist is the single source of truth for what was done and when; update it after every step rather than at the end.
