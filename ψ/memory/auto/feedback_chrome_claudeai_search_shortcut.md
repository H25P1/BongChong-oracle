---
name: feedback-chrome-claudeai-search-shortcut
description: claude.ai's header search icon needs cmd+f, not a bare click, to open a real search input
metadata:
  type: feedback
---

While searching claude.ai (Artifacts gallery, Chats/tasks, Projects) via Chrome browser automation for `kbn-permit-tracker.html` (2026-08-07, see [[project_kbn-permit-tracker]]), clicking the header search icon only surfaced a keyboard-shortcut tooltip, not an active input field. Cost 2-3 wasted screenshot round-trips before finding the working interaction: `cmd+f` opens the real search input.

**Why**: a plain click looking successful (icon responds, tooltip appears) is easy to mistake for "search is now active" — the input isn't actually focused, so subsequent typing goes nowhere.

**How to apply**: on claude.ai browser automation, use `cmd+f` to open search rather than clicking the icon. More generally, verify a search box is actually focused (e.g. via a screenshot or read_page check) before typing into it, rather than assuming a click succeeded.
