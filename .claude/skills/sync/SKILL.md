---
name: sync
description: Commit and push all vault changes to git
disable-model-invocation: true
allowed-tools: Bash
---

Commit and push all changes to the vault.

## Instructions

1. Run `git status` to see what changed
2. If there are changes:
   - Stage all changes with `git add .`
   - Create a commit with a **simple, descriptive message** based on what changed:
     - If notes were added: "Add [note names]"
     - If notes were updated: "Update [note names]"
     - If mixed changes: "Update vault: [brief summary]"
     - Keep it short and readable
   - Push to origin with `git push`
3. If there are no changes, just say "Nothing to sync — vault is up to date"

## Commit message style

- Simple and descriptive
- No prefixes like "chore:", "feat:", etc.
- No emojis
- Examples:
  - "Add new source: Deep Work book"
  - "Update project notes and daily"
  - "Add braindump: AI agent ideas"

## Important

- This is a personal vault, no PRs needed
- Always push directly to main
- Don't ask for confirmation, just do it
