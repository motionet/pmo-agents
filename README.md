# PMO Agents

A collection of AI agent definitions for project management tasks in the `motionet` GitHub organization. These agents run in Claude Code (or any Claude-based coding tool) and use the GitHub CLI (`gh`) to interact with GitHub.

## Prerequisites

- [GitHub CLI](https://cli.github.com/) installed and authenticated (`gh auth login`)
- Access to the `motionet` GitHub organization
- Claude Code (or compatible Claude-based AI tool)

## Structure

```
pmo-agents/
  agents/           ← Agent instruction files
    create-issue.md
  templates/         ← Reusable templates referenced by agents
    prd-issue.md
```

## Available Agents

### Create Issue (`agents/create-issue.md`)

Creates well-structured GitHub issues following a PRD template. Guides you through repo selection, drafting, labeling, milestones, project assignment, and assignees.

**What it does:**
- Takes a short description and turns it into a structured issue
- Suggests repos, labels, and assignees from your org
- Creates missing milestones on the fly
- Always shows a draft for confirmation before posting

## Usage

### In Claude Code / OpenCode

Load the agent instructions at the start of your session:

```
Read agents/create-issue.md and follow those instructions.
I want to create an issue: <your short description>
```

Or copy the agent file into your tool's custom instructions / skills directory for persistent access.

### Tips

- You can be brief — the agent will ask follow-up questions if anything is unclear.
- Mention the repo name if you already know it to skip the selection step.
- Mention a milestone name directly (e.g. "this goes into week12") and the agent will handle creation if it doesn't exist.

## Adding New Agents

1. Create a new `.md` file in `agents/`
2. If the agent needs a template, add it to `templates/`
3. Follow the same structure: behavioral rules, step-by-step flow, exact `gh` commands

## Contributing

All agent definitions are plain Markdown — no code, no dependencies. Edit the `.md` files directly. PRs welcome.
