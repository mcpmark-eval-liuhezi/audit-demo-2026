# audit-demo-2026

Demo repository for the 2026 security review repo-hygiene walkthrough.

## What this repo is for

This is a throwaway example used in a lightning talk about what a
"maintenance audit" of a GitHub repository actually looks like. Rather than
slides, the talk walks through a live repo and audits it, stop by stop.

## The five stops of the audit

1. Default-branch hygiene — branch protection, required reviews, CI status
2. Open pull-request review — stale PRs, missing reviewers, unresolved threads
3. Issue triage — unlabelled, unassigned, or dormant issues
4. Code-scanning alerts — open alerts by severity and tool
5. Notification settings — watch level, mentions, and routing

The working checklist for these stops lives in
[`docs/audit-checklist.md`](docs/audit-checklist.md), and follow-ups found
during the audit are tracked as issues.
