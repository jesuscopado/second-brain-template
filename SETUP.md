# Setup

## Step 1: Install Obsidian

[Obsidian](https://obsidian.md/) is a free note-taking app that works with local markdown files. Download it for your platform:

- **Mac**: `brew install --cask obsidian` or [download](https://obsidian.md/download)
- **Windows**: [Download for Windows](https://obsidian.md/download)
- **Linux**: [Download for Linux](https://obsidian.md/download)
- **Mobile**: Available on iOS and Android (syncs via iCloud or Git)

## Step 2: Install Claude Code

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) is Anthropic's CLI tool that lets Claude work directly with your files. It's the AI agent that powers all the skills in this template.

```bash
npm install -g @anthropic-ai/claude-code
```

You'll need an [Anthropic API key](https://console.anthropic.com/) or a Claude Pro/Max subscription.

## Step 3: Clone this template

```bash
# Option A: Use as GitHub template (recommended)
# Click "Use this template" on GitHub, then clone your copy

# Option B: Clone directly
git clone https://github.com/jesuscopado/second-brain-template.git second-brain
cd second-brain
```

## Step 4: Open in Obsidian

1. Open Obsidian
2. Click **"Open folder as vault"**
3. Select the cloned folder (`second-brain`)
4. Obsidian will ask to trust the plugins — click **"Trust author and enable plugins"**

The template includes pre-configured settings for:
- Daily notes path → `Calendar/`
- Templates path → `x/Templates/`
- Attachments path → `x/Attachments/`
- New files default to `+/` (inbox)

## Step 5: Install community plugins

The template references these plugins. Obsidian will recognize them but you need to install/update them:

1. Go to **Settings → Community plugins → Browse**
2. Search and install each one:

### Required

- **[Dataview](https://github.com/blacksmithgu/obsidian-dataview)** — The engine behind Maps. Lets you write queries in your notes that automatically list, filter, and sort other notes based on their frontmatter. Without this, Maps don't work. Think of it as SQL for your vault.

- **[Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks)** — Turns checkboxes (`- [ ]`) into a full task management system. You write tasks inside any note (projects, dailies, ideas) and Tasks aggregates them from the whole vault. Supports due dates (`📅`), scheduled dates (`⏳`), and done dates (`✅`). The `/daily` skill uses this to show your pending tasks.

- **[Excalidraw](https://github.com/zsviczian/obsidian-excalidraw-plugin)** — A full drawing and diagramming tool embedded in Obsidian. Create flowcharts, mind maps, system diagrams, sketches — all stored as files in your vault. Perfect for visual thinking: map out a project architecture, sketch a concept, or create a visual MOC (Map of Content). Drawings can embed and link to other notes, making them part of your knowledge graph.

### Recommended

- **[Templater](https://github.com/SilentVoid13/Templater)** — Supercharges Obsidian's built-in templates with variables, dates, and logic. When you create a new note from a template, Templater auto-fills `{{date}}` with today's date, can prompt you for input, and more. Makes note creation faster and consistent.

- **[Calendar](https://github.com/liamcain/obsidian-calendar-plugin)** — Adds a calendar widget to the sidebar. Click any date to jump to (or create) that day's daily note. Makes navigating your `Calendar/` folder intuitive instead of scrolling through files.

- **[Git](https://github.com/Vinzent03/obsidian-git)** — Auto-commits and pushes your vault to a Git repo on a schedule (e.g., every 30 minutes). Your vault is always backed up without thinking about it. Also lets you sync between devices via GitHub.

### Optional but game-changing

- **A dictation tool** — This is how I personally use this system: talking instead of typing. Tools like [Wispr Flow](https://ref.wisprflow.ai/jesuscopado), macOS Dictation, or any speech-to-text let you dump ideas into Claude Code by voice. Combined with `/braindump`, you literally talk and your second brain organizes everything. Highly recommended for capturing ideas on the go or when you're too lazy to type.

- **[Advanced Tables](https://github.com/tgrosinger/advanced-tables-obsidian)** — Makes editing markdown tables bearable. Tab to move between cells, auto-formatting, sorting columns. Not essential but saves frustration if you use tables often.

3. Enable each plugin after installing

## Step 6: Run onboarding

Open a terminal in your vault directory and start Claude Code:

```bash
cd second-brain
claude
```

Then run the onboarding skill:

```
/onboarding
```

Claude will interview you (name, role, interests, projects) and personalize `CLAUDE.md` with your context. This is what teaches Claude how YOUR vault works.

## Step 7: Start using it

- **Next morning**: Run `/daily` for your first check-in
- **Got ideas?**: Run `/braindump` and dump everything
- **Found an article?**: Run `/url https://example.com`
- **End of week**: Run `/weekly` for your reflection
- **Vault growing?**: Run `/consolidate` to connect the dots

Delete the example notes (marked with `(example)` in the filename) once you're comfortable.
