# Contributing

Thanks for your interest in improving the Second Brain Template! Here's how you can help.

## Ways to contribute

### 1. New skills

Skills live in `.claude/skills/<name>/SKILL.md` and are invoked with `/name` in Claude Code. If you've built a skill that improves the knowledge management workflow, we'd love to see it.

**To submit a new skill:**
- Create a folder in `.claude/skills/` with a `SKILL.md` file
- Include `name`, `description`, and `allowed-tools` in the frontmatter
- Write clear instructions for Claude (see existing skills for the style)
- Test it in your own vault first
- Open a PR with a description of what the skill does and why it's useful

**Skill sources:**
- [skills.sh](https://skills.sh) — Community skills directory
- Custom skills you've built

### 2. Templates

Note templates live in `x/Templates/`. If you have a useful template for a note type we don't cover, submit a PR.

### 3. Improvements to existing skills

Found a bug or a better workflow? PRs welcome. Please describe what you changed and why.

### 4. Documentation

Better explanations, more examples, translations — all welcome.

## PR guidelines

- **One thing per PR** — don't mix a new skill with a template fix
- **Test first** — make sure your contribution works in a real vault
- **Describe the why** — not just what you changed, but why it's better
- **Keep it simple** — follow the existing style, don't over-engineer

## Style guide

- Skills and templates are written in **English** (content can be in any language)
- Frontmatter fields are always in English (`date`, `status`, `in`)
- Section titles in English (`## Overview`, `## Key ideas`)
- Links integrated in text (Wikipedia-style), never in "Related:" sections
- No emojis in code/templates unless they serve a functional purpose (like Tasks plugin dates)

## Questions?

Open an issue. We'll figure it out together.
