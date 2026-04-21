

# Project Memory — horizon-spotify
> 876 notes | Score threshold: >40

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

## 📝 NOTE: 1 uncommitted file(s) in working tree.\n\n## Active: `snippets`

- **🟢 Edited snippets/theme-styles-variables.liquid (6 changes, 105min)**

## Project Standards

- Updated schema Score — confirmed 3x
- what-changed in brainsync_auto.md — confirmed 3x
- what-changed in brainsync_auto.md — confirmed 3x
- Strengthened types Recent
- Updated schema Score — evolves the database schema to support new requirements — confirmed 3x
- what-changed in shared-context.json — confirmed 4x
- Strengthened types Comprehensive
- what-changed in brainsync_auto.md — confirmed 3x

## Recent Decisions

- decision in task.md

## Learned Patterns

- Always: what-changed in brainsync_auto.md — confirmed 3x (seen 4x)
- Always: what-changed in brainsync_auto.md — confirmed 3x (seen 5x)
- Always: what-changed in brainsync_auto.md — confirmed 3x (seen 6x)
- Agent generates new migration for every change (squash related changes)
- Agent installs packages without checking if already installed

## Available Tools (ON-DEMAND only)
- `sys_core_01(q)` — Deep search when stuck
- `sys_core_05(query)` — Full-text lookup
> Context above IS your context. Do NOT call sys_core_14() at startup.
