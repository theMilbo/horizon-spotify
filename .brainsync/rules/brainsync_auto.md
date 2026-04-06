

# Project Memory — horizon-spotify
> 72 notes | Score threshold: >40

## Safety — Never Run Destructive Commands

> Dangerous commands are actively monitored.
> Critical/high risk commands trigger error notifications in real-time.

- **NEVER** run `rm -rf`, `del /s`, `rmdir`, `format`, or any command that deletes files/directories without EXPLICIT user approval.
- **NEVER** run `DROP TABLE`, `DELETE FROM`, `TRUNCATE`, or any destructive database operation.
- **NEVER** run `git push --force`, `git reset --hard`, or any command that rewrites history.
- **NEVER** run `npm publish`, `docker rm`, `terraform destroy`, or any irreversible deployment/infrastructure command.
- **NEVER** pipe remote scripts to shell (`curl | bash`, `wget | sh`).
- **ALWAYS** ask the user before running commands that modify system state, install packages, or make network requests.
- When in doubt, **show the command first** and wait for approval.

**Stack:** Unknown stack

## 📝 NOTE: 1 uncommitted file(s) in working tree.\n\n## Important Warnings

- **gotcha in agent-rules.md** — File updated (external): .brainsync/agent-rules.md

Content summary (3

## Active: `snippets`

- **Replaced auth SIHO**
- **trade-off in jewelry-icons.liquid**
- **what-changed in jewelry-icons.liquid**

## Project Standards

- Strengthened types Tidl
- what-changed in shared-context.json — confirmed 4x
- Strengthened types Updated — ensures atomic multi-step database operations
- Strengthened types Tidl
- Strengthened types HEAD
- Updated day database schema — introduces API versioning for backward compatib... — confirmed 3x
- Strengthened types Project
- what-changed in shared-context.json — confirmed 3x

## Verified Best Practices

- Agent generates new migration for every change (squash related changes)
- Agent installs packages without checking if already installed

## Available Tools (ON-DEMAND only)
- `query(q)` — Deep search when stuck
- `find(query)` — Full-text lookup
> Context above IS your context. Do NOT call load() at startup.
