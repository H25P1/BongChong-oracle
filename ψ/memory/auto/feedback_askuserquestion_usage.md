---
name: feedback-askuserquestion-usage
description: Two AskUserQuestion misuses caught in the same session — unevidenced Recommended tags and forcing open-ended questions into fixed options
metadata:
  type: feedback
---

**Rule 1 — don't mark an option "(Recommended)" without a cheap feasibility check first.** When asked to fetch `kbn-permit-tracker.html` from claude.ai, presented three options (browser automation / manual download / paste) and tagged "browser automation" Recommended purely because it sounded most capable — without checking whether the target artifact was even reachable from the account. It wasn't; ~10 tool calls across Artifacts/Chats/Projects came up empty.

**Why**: a confident-sounding recommendation with no supporting evidence costs the human more than an honest "let me verify this is feasible first." See [[project_kbn-permit-tracker]] for the concrete case this happened on.

**How to apply**: before tagging any AskUserQuestion option Recommended — especially one that fetches/locates external content across a system not yet probed — do a 30-second existence check, or downgrade the framing to "untested, but likely fastest if it works." Any recommendation that implicitly claims "this will work" needs that claim checked for plausibility first, not just verified before promising results.

**Rule 2 — reserve AskUserQuestion's fixed-option UI for genuinely discrete choices.** During `/awaken`, tried to ask for the Oracle's "purpose" as a multiple-choice AskUserQuestion; the tool rejected it because an open-ended field can't honestly be reduced to ≥2 discrete options. Had to fall back to a plain chat message mid-flow.

**How to apply**: route open-ended, single-answer questions (a name, a purpose, a freeform description) through plain conversational text from the start rather than forcing them into AskUserQuestion and eating a rejected call.
