---
name: avalonia-dependency-upgrade
description: Workflow command scaffold for avalonia-dependency-upgrade in downkyicore.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /avalonia-dependency-upgrade

Use this workflow when working on **avalonia-dependency-upgrade** in `downkyicore`.

## Goal

Upgrades the Avalonia UI framework version and updates related dependencies.

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
- Optionally update README.md or related files to reflect new version.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.