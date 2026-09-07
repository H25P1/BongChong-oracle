# Memory Index

Auto-loaded every session. Keep entries to one line each; link to the full file for detail.
Convention adopted fleet-wide 2026-09-07 (matches Horacle/Argon) — see `ψ/inbox/` for the notification explaining why and how to use it.

## User — who H is

## Project — what we're working on

- [KBN solar/EV permit tracker](project_kbn-permit-tracker.md) — handoff intake done; blocked locating the .html artifact (not on claude.ai gallery/chats/projects, not in local sandbox).

## Reference — where things live externally

## Feedback — environment + tooling gotchas

- [AskUserQuestion usage](feedback_askuserquestion_usage.md) — don't tag "(Recommended)" without a feasibility check; route open-ended questions to plain text, not fixed options.
- [Branch protection by convention](feedback_branch_protection_by_convention.md) — unfamiliar repo's `main` can be hook-protected even when GitHub's API shows `protected: false`; default to feature-branch+PR first try.
- [Stale fact propagation](feedback_stale_fact_propagation.md) — check an external doc's own last-updated date before copying a count/date/status downstream.
- [Backup untracked files before rename sweeps](feedback_backup_untracked_before_rename.md) — untracked files have no git undo; back up before multi-file edits.
- [Sandbox blocks ~/Desktop and ~/Downloads](feedback_sandbox_local_file_access.md) — only files H explicitly shares are Read-able; probe early before offering "give me the local path."
- [claude.ai search needs cmd+f](feedback_chrome_claudeai_search_shortcut.md) — clicking the header search icon only shows a tooltip, doesn't focus an input.
