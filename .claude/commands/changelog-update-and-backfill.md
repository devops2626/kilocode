---
name: changelog-update-and-backfill
description: Workflow command scaffold for changelog-update-and-backfill in kilocode.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /changelog-update-and-backfill

Use this workflow when working on **changelog-update-and-backfill** in `kilocode`.

## Goal

Keeps changelog files up to date by adding or backfilling .changeset entries and updating package CHANGELOG.md files.

## Common Files

- `.changeset/*.md`
- `packages/*/CHANGELOG.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update one or more .changeset/*.md files describing changes.
- Update corresponding packages/*/CHANGELOG.md files with new entries.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.