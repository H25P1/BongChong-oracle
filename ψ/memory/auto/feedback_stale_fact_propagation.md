---
name: feedback-stale-fact-propagation
description: Check an external doc's own last-updated date before copying a count/date/status from it into multiple downstream files
metadata:
  type: feedback
---

During `/awaken` (2026-08-06), the Oracle family's "76+" member count was copied from mother-oracle's Issue #60 into three internal files and a public GitHub announcement — without checking that the issue was stamped "Last Updated: 2026-02-04," six months stale. The correct figure (280+) was already sitting in the same conversation's confirm screen. Fixing it required a second PR and an edit to an already-posted public issue. Caught by `advisor()`, not by self-verification at the time of copying.

**Why**: the cost of a stale figure compounds with every file — and especially every public post — it lands in before being caught. A fresher number was already available in context and wasn't cross-checked against the external source.

**How to apply**: before copying a count, date, or status from an external document into multiple downstream places, check that document's own last-updated timestamp first — especially when a fresher number might already be sitting elsewhere in the current conversation.
