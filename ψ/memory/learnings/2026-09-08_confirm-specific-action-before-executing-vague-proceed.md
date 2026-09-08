---
pattern: When a vague "proceed" follows a chain of steps, restate the specific hard-to-reverse action about to execute before doing it — don't let a permission classifier be the only backstop
date: 2026-09-08
source: "rrr: BongChong-oracle"
concepts: [approval-ambiguity, git-hooks, branch-protection, standup-priority]
---

# Confirm the specific action before executing a vague "proceed"

A user's "proceed as recommended" / "ดำเนินการตามแนะนำได้เลยครับ" after a chain of
actions does not unambiguously authorize the most recent hard-to-reverse step in that
chain. In this session it was read as "merge the open PR" when the prior message had
only said "merge it whenever you're ready" — informational, not a recommendation. The
auto-mode classifier blocked the merge attempt; the AI's own judgment did not catch the
ambiguity first.

**Rule**: before executing a shared/hard-to-reverse action (PR merge, force-push,
schema change) triggered by ambiguous natural-language approval, restate the specific
action about to happen ("this means merging PR #N into main — proceed?") and wait for
confirmation on that restated action — even when a permission classifier exists as a
backstop. The backstop existing is not a reason to skip the explicit check; it caught
this one, but should not be relied on as the primary safeguard.

**Related**: before attempting push/merge in an unfamiliar repo, check for local git
hooks (`ls .git/hooks/`) first — a `safety-check.sh` blocking direct push to `main` was
only discovered via a failed attempt here, costing a round-trip. See
[[feedback_branch_protection_by_convention]].

**Also related**: when another Oracle's inbox message explicitly defers a decision to
you (not auto-resolved on your behalf), treat it as the lead item in a standup, not a
footnote after routine sections like "no open issues."
