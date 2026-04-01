---
name: avalonia-dependency-update
description: Workflow command scaffold for avalonia-dependency-update in downkyicore.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /avalonia-dependency-update

Use this workflow when working on **avalonia-dependency-update** in `downkyicore`.

## Goal

Updates the Avalonia UI framework version and sometimes related documentation.

## Common Files

- `Directory.Packages.props`
- `README.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update Directory.Packages.props with new Avalonia version.
- Optionally update README.md or other related files.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.