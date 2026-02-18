---
name: daily
description: Morning check-in + day briefing
allowed-tools: Read, Glob, Write, AskUserQuestion, ToolSearch
---

Good morning! Let's start the day right. Do the following IN THIS ORDER:

## Part 1: Personal check-in (first things first)

Ask warmly:
1. **How did you sleep last night?** (good/okay/bad, approximate hours)
2. **How are you feeling right now?** (energy, mood)
3. **Anything on your mind or worrying you?**
4. **3 things you're grateful for today** (can be small)

Tone: warm, genuine, like a friend who actually cares. No empty formulas.

## Part 2: Day briefing

Once the check-in is done:
1. **Pending tasks**: Search for checkboxes `- [ ]` across the vault (use Grep for `- \[ \]`). List the ones with 📅 coming up or the most relevant ones.
2. **Active projects**: Read `Projects/On/` and `Projects/Ongoing/` — list only those with urgent tasks or upcoming deadlines.
3. **Quick motivation**: Something brief and real, not cheesy.

## Part 3: Save the check-in

Save everything in `Calendar/YYYY-MM-DD.md` with this format:

```markdown
---
date: YYYY-MM-DD
type: daily-checkin
---

## Check-in

**Sleep**: [response]
**State**: [response]
**On my mind**: [response]

**Gratitude**:
1. [thing 1]
2. [thing 2]
3. [thing 3]

## Focus for today

[Based on tasks, projects, and what matters — what should they prioritize today]

## Pending tasks

TASKS_BLOCK
```

IMPORTANT: When writing the daily, replace TASKS_BLOCK with a code block with language "tasks" and content "not done" (triple backticks). This makes the Tasks plugin show all pending tasks.

If today's note already exists, append without overwriting.
