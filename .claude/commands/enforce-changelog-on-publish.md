---
name: enforce-changelog-on-publish
description: Workflow command scaffold for enforce-changelog-on-publish in kilocode.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /enforce-changelog-on-publish

Use this workflow when working on **enforce-changelog-on-publish** in `kilocode`.

## Goal

Prevents publishing unless changelog updates are present by modifying publishing scripts and adding .changeset entries.

## Common Files

- `.changeset/*.md`
- `script/publish.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update a relevant .changeset/*.md file.
- Modify script/publish.ts to enforce changelog requirements.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.