---
pattern: When presenting an AskUserQuestion option as "(Recommended)", only do so after a cheap existence/feasibility check — not because it sounds like the most capable approach
date: 2026-08-07
source: "rrr: BongChong-oracle"
concepts: [ask-user-question, evidence-before-confidence, browser-automation, fetch-external-content]
---

# Recommend only with evidence, not confidence

When H asked to pull a file (`kbn-permit-tracker.html`) known to exist on claude.ai into
this repo, I presented three options via `AskUserQuestion` — browser automation, manual
download, paste content — and marked "browser automation" **(Recommended)**. I had not
checked whether the target artifact was actually reachable from the logged-in account.
It wasn't: after ~10 tool calls across Artifacts gallery, Chats/tasks search, and
Projects, nothing matched. The recommendation was styling ("sounds most capable, most
automated"), not evidence.

**Why**: A confident-sounding recommendation with no supporting check costs the human
more than an honest "let me verify this is feasible first." The cheaper move was either
a 30-second existence check before presenting options, or asking a direct factual
question ("is this file only on claude.ai, or do you also have it locally?") instead of
routing straight to the most automated-sounding path.

**How to apply**: Before marking any option "(Recommended)" in an AskUserQuestion —
especially options that involve fetching/locating external content across a system you
haven't yet probed — do a cheap feasibility check first, or downgrade the framing to
"untested, but likely fastest if it works" rather than an unqualified Recommended tag.
This generalizes beyond browser automation: any time a recommendation implicitly claims
"this will work," verify that claim is at least plausible before making it, not just
before promising results.
