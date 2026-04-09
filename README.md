# MinimumViableThinking

Shared AI workflows for TryHackMe's Product and Design team.

This repo packages the prompts, commands, and context that make Claude Code useful across the team — so everyone benefits from the same foundation instead of starting from scratch.

---

## What's in here

| File / Folder | Purpose |
|---|---|
| `CLAUDE.md` | Shared TryHackMe context — product knowledge, segments, squad structure, principles |
| `commands/` | Slash commands for common PM and design workflows |

---

## How to use it

### Step 1 — Clone the repo

```bash
git clone https://github.com/Laris-0/MinimumViableThinking.git
```

### Step 2 — Add CLAUDE.md to your project

Copy or symlink `CLAUDE.md` into the root of your working directory. Claude Code reads this automatically and uses it as shared context for every conversation in that project.

### Step 3 — Add commands to Claude Code

Copy the files from `commands/` into your Claude Code commands folder:

```
~/.claude/commands/
```

Once added, you can trigger any command by typing `/command-name` in Claude Code.

---

## Available Commands

### Discovery & Strategy
| Command | What it does | Framework |
|---|---|---|
| `/opportunity-map` | Build an Opportunity Solution Tree from outcome to testable solutions | Teresa Torres OST |
| `/assumption-test` | Surface and stress-test riskiest assumptions before building | Teresa Torres |
| `/research-brief` | Create a hypothesis-driven research brief | Continuous discovery |
| `/interview-guide` | Generate a past-story interview guide for continuous discovery | Teresa Torres |
| `/synthesize-interviews` | Turn raw interview notes into themed insights and opportunities | Research synthesis |

### Documentation
| Command | What it does | Framework |
|---|---|---|
| `/write-prd` | Draft a 1-pager or full PRD | Lenny Rachitsky + Marty Cagan |
| `/summarize-for-notion` | Turn raw research into a polished Notion doc | Research synthesis |
| `/draft-comms` | Draft Slack updates, stakeholder comms, or announcements | BLUF format |

### Execution
| Command | What it does | Framework |
|---|---|---|
| `/write-ticket` | Write a structured engineering ticket with user story and outcome link | Marty Cagan 4 pillars |
| `/figma-to-tickets` | Turn Figma designs into Linear tickets | — |
| `/debug-and-escalate` | Reproduce a bug and produce a Notion incident doc + Jira ticket | — |

### AI & Prompt Work
| Command | What it does |
|---|---|
| `/split-prompt` | Diagnose and separate an overloaded AI prompt |

### Session Management
| Command | What it does |
|---|---|
| `/session-wrap` | Capture decisions, learnings, and next steps before ending a session |

---

## Contributing

If you improve a command or create a new one that's useful for the team, open a PR. Keep commands focused — one job per command.

If something in `CLAUDE.md` is outdated, update it. This file is only useful if it reflects how the product and team actually work today.
