---
name: feedback-sandbox-local-file-access
description: Local filesystem sandbox blocks Read/ls/find on ~/Desktop and ~/Downloads except a file H explicitly shared
metadata:
  type: feedback
---

While trying to locate `kbn-permit-tracker.html` (2026-08-07, see [[project_kbn-permit-tracker]]), `Read` worked on the one handoff file H explicitly shared from `~/Downloads`, but `ls`/`find`/`Read` on any other file in the same folder (or in `~/Desktop`) failed with EPERM. This was only discovered mid-task, not checked upfront.

**Why**: the handoff doc's claim that a file was saved to "the user's desktop" could plausibly mean the literal `~/Desktop` folder — but even if so, this sandbox can't reach it. Knowing this boundary upfront changes which options are worth offering H at all.

**How to apply**: when a task might require reading local files outside what H has directly attached or pasted, check the sandbox boundary early (a quick `ls` probe) rather than assuming general filesystem access — and skip presenting "give me the local path" as an option if the path is likely to sit in a directory this sandbox can't read.
