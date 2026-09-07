---
name: feedback-backup-untracked-before-rename
description: Back up untracked files before an identity-wide rename/edit sweep — they have no git undo
metadata:
  type: feedback
---

During an identity-rename sweep (2026-08-07), `advisor()` flagged that 3 of 11 target files were untracked before any edits were made — those files have no git safety net if the sweep goes wrong. Untracked files were backed up to scratchpad before proceeding.

**Why**: a tracked file can be reverted with `git checkout`/`git diff` if a sweep-wide find/replace goes wrong; an untracked file cannot. This is cheap insurance that shouldn't need an advisor call to catch every time.

**How to apply**: before any multi-file rename or content sweep, run `git status` and note which target files are untracked (`??`). Back those up (copy to scratchpad, or `git add` them first if appropriate) before editing, as a reflex — not something to rely on `advisor()` to catch.
