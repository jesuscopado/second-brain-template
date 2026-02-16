---
name: weekly
description: Weekly reflection — review the week, synthesize, and plan the next one
disable-model-invocation: true
allowed-tools: Read, Write, Edit, Glob, Grep, AskUserQuestion, ToolSearch
---

Time for the weekly reflection. Review the week, find patterns, and help plan the next one.

## Step 1: Calculate week range

Calculate Monday to Sunday of the current week (or last week if today is Monday). Format: `YYYY-MM-DD`.

## Step 2: Gather information

Read everything relevant from the week:

1. **Dailies**: Read `Calendar/YYYY-MM-DD.md` files for the range (Mon-Sun). Use Glob to find which ones exist.
2. **Recent logs**: Search `Calendar/Logs/` for files created this week.
3. **Active projects**: Read projects in `Projects/On/` and `Projects/Ongoing/`.
4. **Tasks**: Search for completed checkboxes (`- [x]`) and pending ones (`- [ ]`) across the vault with Grep.
5. **Notes created**: Search for notes with `date: YYYY-MM-DD` from this week in `Atoms/`.

## Step 3: Analyze the week

Synthesize into these categories:

### Wins
What went well? Concrete achievements, completed tasks, project progress.

### Blockers
What got stuck? Tasks that didn't move, recurring problems.

### Recurring themes
What patterns do you see? Topics across multiple days, energy trends.

### Task balance
- Completed this week: X
- Overdue (past due date): X
- New created: X

### Vault health
- Notes created this week: X
- Orphan Things (no inlinks): check if there are notes nobody links to

## Step 4: Reflection

Compare the week against current priorities and active projects:
- Are you making progress on what matters?
- Is anything urgent eating time from what's important?
- How was overall energy?

## Step 5: Proposals for next week

Suggest 3-5 concrete priorities for next week, based on:
- What's still pending
- Current priorities
- What the user mentioned during the week

## Step 6: Discuss

Present the full analysis and ask:
- Would you add anything I didn't catch?
- Do the priorities for next week feel right?
- Want to adjust anything?

## Step 7: Save the reflection

Once agreed, save to `Calendar/Logs/YYYY-MM-DD - Weekly YYYY-Wnn.md` where:
- `YYYY-MM-DD` is today's date
- `YYYY-Wnn` is the ISO week number (e.g., `2026-W07`)

Format:

```markdown
---
date: YYYY-MM-DD
type: weekly-review
week: YYYY-Wnn
---

## Wins
- [win 1]
- [win 2]

## Blockers
- [blocker 1]

## Recurring themes
- [theme 1]

## Balance
- Tasks completed: X
- Tasks overdue: X
- Notes created: X

## Reflection
[Paragraph reflecting on alignment with priorities]

## Next week
- [ ] [priority 1]
- [ ] [priority 2]
- [ ] [priority 3]
```
