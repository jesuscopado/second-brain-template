---
name: onboarding
description: Set up your Second Brain — personalize CLAUDE.md with your info
disable-model-invocation: true
allowed-tools: Read, Write, Edit, Glob, Grep, AskUserQuestion
---

Welcome! Let's set up your Second Brain. You'll interview the user to personalize the vault.

## Step 1: Introduction

Say:
> Welcome to your Second Brain! I'm going to ask you a few questions to personalize the vault. This will take about 5 minutes.
>
> The more context you give me, the better I can help you. Feel free to paste your CV, LinkedIn bio, or anything that describes what you do.

## Step 2: Interview

Ask these questions ONE AT A TIME (don't overwhelm):

1. **What's your name?**
2. **What do you do?** (Role, company, field. Encourage: "Feel free to paste your LinkedIn headline, CV, or a quick bio.")
3. **What are your main focus areas or interests?** (What topics do you want to track in your second brain?)
4. **What projects are you working on right now?** (Personal, professional, side projects — anything that takes your energy)
5. **What email(s) do you use?** (For calendar integration if they want it)

## Step 3: Personalize CLAUDE.md

Read `CLAUDE.md` and update the "About the owner" section with the user's info:

```yaml
## About the owner
- **Name**: [their name]
- **Role**: [their role]
- **Focus areas**: [their interests]
- **Email**: [their email]
```

## Step 4: Create their Person note

Create a note in `Atoms/People/[Their Name].md` using the Person template:

```yaml
---
date: [today]
in:
---

[Brief description based on what they shared — role, interests, background]
```

## Step 5: Set up initial projects

For each project they mentioned, create a note in the appropriate intensity folder:
- Ask: "For each project, how active is it right now?" and explain the intensity levels (On/Ongoing/Simmering/Sleeping)
- Use the Project template from `x/Templates/Project.md`

## Step 6: Suggest Maps

Based on their interests and projects, suggest 2-3 Maps to create. Only create if they agree.

## Step 7: Wrap up

Say:
> Your Second Brain is ready! Here's what I set up:
> - [list of what was created]
>
> Try `/daily` tomorrow morning to start your first day. Or use `/braindump` right now to dump any ideas you have.

## Tone

Friendly, patient, encouraging. This is their first interaction with the system — make it feel welcoming, not overwhelming.
