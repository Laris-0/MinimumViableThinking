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

## Two layers — Thinking and Artifact

Commands are organised in two layers that compose together:

- **Thinking skills** (`/thinking:*`) are pure Socratic dialogues. They ask questions, pressure-test your direction, and never produce a deliverable. Their output is *sharpened inputs* — your own answers, reorganised — that you carry into the artifact layer.
- **Artifact skills** (everything else) produce deliverables — PRDs, tickets, research briefs, opportunity maps.

Use them together: run `/thinking:strategy` first to pressure-test your thinking, then run `/write-prd` with the sharpened inputs. The thinking layer keeps the AI from jumping to conclusions; the artifact layer produces the document once your inputs are sharp.

---

## Available Commands

### Thinking skills (Socratic dialogue — no artifacts)

Pure question-and-answer dialogues. Every thinking skill follows the same 4-phase pattern: **Frame** (1 question, state the direction in one sentence) → **Probe** (2–3 adaptive questions on underlying logic) → **Stress-test** (2–3 adaptive questions pushing back) → **Sharpen** (you restate, AI surfaces one blind spot, outputs a transcribed sharpened-inputs block in your own words).

Hard rules every thinking skill enforces: one question at a time, no AI opinion until the final phase, no artifact ever produced.

| Command | What it does |
|---|---|
| `/thinking:strategy` | Pressure-test a strategic direction before you commit — useful before writing a vision doc, roadmap narrative, or strategy paper |

### Discovery & Strategy
| Command | What it does |
|---|---|
| `/opportunity-map` | Map from a desired outcome to testable solutions |
| `/assumption-test` | Surface and stress-test riskiest assumptions before building |
| `/research-brief` | Create a hypothesis-driven research brief |
| `/interview-guide` | Generate a past-story interview guide |
| `/synthesize-interviews` | Turn raw interview notes into themed insights and opportunities |

### Documentation
| Command | What it does |
|---|---|
| `/write-prd` | Draft a 1-pager or full PRD |
| `/summarize-for-notion` | Turn raw research into a polished Notion doc |
| `/draft-comms` | Draft Slack updates, stakeholder comms, or announcements |

### Execution
| Command | What it does |
|---|---|
| `/write-ticket` | Write tickets from a user problem or Figma design (future: Speckit integration) |

### AI & Prompt Work
| Command | What it does |
|---|---|
| `/split-prompt` | Diagnose and separate an overloaded AI prompt |

### Session Management
| Command | What it does |
|---|---|
| `/session-wrap` | Capture decisions, learnings, and next steps before ending a session |

### Onboarding
| Command | What it does |
|---|---|
| `/onboard` | Welcome a new PM or designer and guide them through tool access and first commands |

---

## Contributing

If you improve a command or create a new one that's useful for the team, open a PR. Keep commands focused — one job per command.

If something in `CLAUDE.md` is outdated, update it. This file is only useful if it reflects how the product and team actually work today.
