---
pattern: "Check an external doc's last-updated date before copying its facts downstream; treat unfamiliar repos' main branch as protected-by-convention until proven pushable"
date: 2026-08-06
source: "rrr: bonne-chance-oracle"
concepts: ["awaken", "verification", "git-workflow", "stale-data"]
---

# Stale-fact propagation and branch-protection-by-convention

During Bonne chance Oracle's `/awaken` (Full Soul Sync), two generalizable mistakes surfaced:

## 1. Stale fact propagation

Copied the Oracle family's "76+" member count from mother-oracle's Issue #60 into three files and a public GitHub announcement, without checking that the issue was stamped "Last Updated: 2026-02-04" — six months stale. The correct figure (280+) was already sitting in the same conversation's confirm screen. The fix required a second PR and an edit to an already-posted public issue.

**Rule**: before copying a count, date, or status from an external document into multiple downstream places, check that document's own last-updated timestamp — especially when a fresher number is already available elsewhere in context. The cost of a stale figure compounds with every file (and especially every public post) it lands in before being caught.

## 2. Branch protection by convention, not GitHub settings

`git push origin main` was rejected by a local safety hook (not GitHub branch protection — `gh api repos/.../branches` showed `protected: false`) enforcing an alpha-branch + PR flow for every repo except two named exceptions. There was no discoverable signal beforehand (no README, no CONTRIBUTING.md) — the first push attempt was the only way to learn the convention.

**Rule**: on the first commit to an unfamiliar repo, default to a feature-branch + PR pattern rather than assuming `main` is directly pushable — local safety policy can enforce conventions invisible to GitHub's own API.
