---
name: feedback-branch-protection-by-convention
description: An unfamiliar repo's main branch can be protected by local hook convention, not GitHub settings — treat it as protected until proven pushable
metadata:
  type: feedback
---

`git push origin main` was rejected during `/awaken` (2026-08-06) by a local safety hook enforcing an alpha-branch + PR flow for every repo except two named exceptions — not GitHub branch protection (`gh api repos/.../branches` showed `protected: false`). There was no discoverable signal beforehand (no README, no CONTRIBUTING.md); the first push attempt was the only way to learn the convention.

**Why**: local safety policy can enforce conventions that are invisible to GitHub's own API, so checking `protected: false` doesn't mean `main` is actually pushable.

**How to apply**: on the first commit to an unfamiliar repo, default to a feature-branch + PR pattern rather than assuming `main` is directly pushable. If `git push origin main` is rejected, treat that as the expected discovery mechanism, not an exceptional failure — read the hook's error message for the required branch/PR pattern and follow it.
