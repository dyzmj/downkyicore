---
name: release-version-bump
description: Workflow command scaffold for release-version-bump in downkyicore.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /release-version-bump

Use this workflow when working on **release-version-bump** in `downkyicore`.

## Goal

Prepares a new release by updating versioning and changelog files.

## Common Files

- `CHANGELOG.md`
- `DownKyi/Models/AppInfo.cs`
- `script/macos/Info.plist`
- `version.txt`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update CHANGELOG.md with new changes.
- Update DownKyi/Models/AppInfo.cs with new version info.
- Update script/macos/Info.plist with new version.
- Update version.txt with new version number.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.