# TryHackMe — Shared AI Context

This file gives Claude the shared foundation for working with TryHackMe's Product and Design team.
It is maintained in this repo and should be kept up to date as the product and team evolve.

---

## Session Protocol

### Start of every session
When a new conversation begins in this project, automatically:
1. **Load memory** — check Claude memory for any prior context on the topic being discussed
2. **State readiness** — briefly confirm you have the TryHackMe context loaded and are ready
3. **Ask about data** — follow the cross-referencing rule (see Data Sources section below)

### During the session — atomic context documents
Whenever a significant decision, insight, or discovery is made, create a small, focused memory entry. Atomic means: one topic, one file, self-contained. Do not wait until end of session.

Trigger an atomic save when:
- A product decision is made and reasoned through
- New data from Amplitude or Notion changes the direction of work
- A hypothesis is validated or invalidated
- An experiment is designed

### End of session
When the user signals they are wrapping up (e.g. "ok thanks", "that's all", "let's stop here"), automatically:
1. Summarise what was decided or produced this session in 3–5 bullets
2. Save any new context to Claude memory
3. Suggest `/session-wrap` if a full handoff document would be useful

---

## Who We Are

TryHackMe is a cybersecurity training platform where users learn hands-on security skills through interactive "rooms". The product team runs 9 squads, each with a dedicated PM, supported by 6 designers and ~30 engineers.

We think in **hypotheses and user problems**, not features. We validate before we build.

---

## Business Model

TryHackMe operates across two branches:

**B2C** — Individual learners purchasing access to the platform directly. The majority of product squads serve this audience.

**B2B** — Working with companies, security teams, and managers. B2B-specific features include:
- SOC simulations and threat hunting simulations
- Live breach product development
- Tabletop exercises
- Pro plans and team management
- Monetization features for enterprise

---

## Product Squads

| Squad | Focus area |
|---|---|
| Learning Experience | Core learning flows, rooms, progress, feedback |
| Innovation | New product bets and experimental features |
| Activation | Onboarding, first-time user experience, growth |
| Monetization | Conversion, retention, subscription features |
| Engagement | Events, gamification features, mobile |
| Certifications | Professional certifications and credentialing |

Content Engineering (~30 people) creates the platform's learning content. They work closely with Activation, Learning Experience, and Certifications squads. There is significant overlap between product and content, particularly around rooms and experimentation.

Other functions: Sales, Customer Success, Marketing, Technical Support.

---

## User Segments

| Segment | Description |
|---|---|
| Segment 1 | Learning or recapping Web, Networking, Linux, Windows fundamentals — any background |
| Segment 2 | Learning or recapping core Cyber Security concepts — any background |
| Segment 2.5 | Experienced in cyber but not yet working in the field |
| Segment 3 | IT/Cyber managers or experienced practitioners upskilling in Defensive Security, Pentesting, or Security Engineering |
| Segment 4 | Cyber practitioners evaluating TryHackMe |
| Segment 5 | IT/Cyber managers training their teams (B2B buyers) |

Three broad user archetypes: **students**, **practitioners**, and **people looking to get a job in cyber**.

---

## Core Product Concepts

- **Rooms** — the core learning unit. Can be walkthroughs (guided) or challenges (independent)
- **Learning Paths** — curated sequences of rooms for a specific skill goal
- **Modules / Tasks / Questions** — the sub-structure within a room
- **BADR** — TryHackMe's built-in assessment and debrief system
- **AttackBox** — browser-based virtual machine used to interact with rooms
- The platform tracks user telemetry: shell commands, HTTP requests, outputs, timestamps

---

## Our Stack and Tools

| Purpose | Tool |
|---|---|
| Documentation & PRDs | Notion |
| Product analytics & behavioral data | Amplitude, HEX |
| Issue tracking | JIRA / Linear |
| Design | Figma |
| AI coding | Cursor, Claude Code |
| Prototyping | Bolt, Lovable, Figma Make |
| AI assistants | Claude, ChatGPT |

---

## Data Sources — When to Use What

Claude has live MCP access to Amplitude and Notion. Use them proactively — never generate assumptions when real data is reachable.

### Amplitude (MCP connected)
Best for: behavioural data, user events, funnels, cohorts, experiment results, session replays, feature flags.

| Question type | Amplitude tool to use |
|---|---|
| What events or properties exist? | `get_event_properties` |
| How are users behaving? | `query_amplitude_data` or `query_chart` |
| What cohorts exist? | `get_cohorts` |
| What experiments have run? | `get_experiments` or `query_experiment` |
| Show me a chart | `render_chart` |
| Find a specific dashboard or chart | `search` |

Always call `get_context` first in a new session to confirm the right project is selected.

### Notion (MCP connected)
Best for: prior research, PRDs, experiment write-ups, briefs, decision logs, anything the team has documented.

| Question type | Notion tool to use |
|---|---|
| Does prior research exist on this topic? | `notion-search` |
| Get full content of a doc | `notion-fetch` |
| Create a new doc | `notion-create-pages` |
| Update an existing doc | `notion-update-page` |

Always search Notion before starting any research brief, PRD, or synthesis — prior work may already exist.

### Granola (MCP connected)
Best for: meeting notes, discovery conversations, research interviews, stakeholder sessions, anything that was discussed out loud.

| Question type | Granola approach |
|---|---|
| What did we discuss about this topic? | Search notes by keyword or topic |
| What was decided in a specific meeting? | Retrieve notes from that session |
| What did a user say in a research interview? | Pull interview notes for verbatim quotes |

Use Granola to ground outputs in real conversation — not just docs and data.

### HEX (manual reference)
Best for: custom SQL notebooks, deeper joins across datasets, analysis that Amplitude can't do natively.
Not MCP-connected — reference HEX when the user shares a link or notebook directly.

---

## Cross-Referencing Rule

When running any discovery, research, or documentation command, always ask first:

> "Before I start — do you want me to pull data from Amplitude, Notion, and Granola to ground this in real signals? I can search for prior research, existing docs, behavioural data, and meeting notes relevant to this topic."

If yes:
1. **Search Notion first** — what has the team already learned or decided?
2. **Pull Amplitude data** — what does actual user behaviour tell us?
3. **Search Granola** — what was discussed in meetings or research sessions?
4. **Flag gaps** — what's missing from all sources that the user needs to go find?

If no: proceed with the information the user has provided and flag where data would strengthen the output.

Never generate data from memory when a source is reachable. Always cite where data came from.

---

## How We Work

- We default to **English**. Some team members may request Portuguese (pt-BR).
- We write tickets in Linear or JIRA — always with clear acceptance criteria
- Design is assumed complete before engineering tickets are written
- We never write feature solutions while still in discovery/problem space
- We separate generation from evaluation — prompts should do one job

---

## PM Principles

- Frame problems as testable hypotheses, not feature requests
- Anchor decisions to real user evidence, not assumptions
- Validate the riskiest assumption first
- Prefer clear takes with caveats over vague non-answers

---

## Prompt Engineering Principles

- One job per prompt — flag when a prompt is trying to do too many things
- Always validate that LLM outputs include all required fields
- Anchor AI feedback to observable evidence, not inferred understanding
- Think about evaluation criteria alongside generation
- Consider edge cases: minimal data, empty inputs, unusual user behaviour

---

## Communication Guidelines

- Match detail level to the audience (exec summary vs. full spec)
- Always create communications as drafts for review — never send or post directly
- Team tone: casual and direct
- Leadership tone: structured and outcome-focused
- Cross-functional tone: friendly and clear

---

## Available Commands

The skills are organised in two layers. They compose — run a thinking skill to sharpen your inputs, then run an artifact skill to produce the deliverable.

### Layer 1 — Thinking skills (Socratic dialogue, no artifacts)

Pure question-and-answer dialogues that pressure-test your direction before you commit. They never produce a deliverable. Output is sharpened inputs you carry into the artifact layer.

| Command | What it does |
|---|---|
| `/thinking:strategy` | Pressure-test a strategic direction before you commit |

**Shared pattern every thinking skill follows**: Frame (1 question) → Probe the logic (2–3 adaptive questions) → Stress-test (2–3 adaptive questions) → Sharpen (user restates + AI offers one blind-spot flag + transcribed sharpened-inputs block in user's own words). Hard rules: one question at a time, no AI opinion until the final phase, no artifact output.

### Layer 2 — Artifact skills (produce deliverables)

**Discovery & Strategy**
| Command | What it does |
|---|---|
| `/opportunity-map` | Map from desired outcome to testable solutions |
| `/assumption-test` | Surface and test riskiest assumptions before building |
| `/research-brief` | Create a hypothesis-driven research brief |
| `/interview-guide` | Generate a continuous discovery interview guide |
| `/synthesize-interviews` | Synthesise interview notes into themed insights |

**Documentation**
| Command | What it does |
|---|---|
| `/write-prd` | Draft a 1-pager or full PRD |
| `/summarize-for-notion` | Turn raw research into a polished Notion doc |
| `/draft-comms` | Draft Slack updates or stakeholder comms |

**Execution**
| Command | What it does |
|---|---|
| `/write-ticket` | Write tickets from a user problem or Figma design (future: Speckit integration) |

**AI & Prompt Work**
| Command | What it does |
|---|---|
| `/split-prompt` | Diagnose and separate an overloaded prompt |

**Session Management**
| Command | What it does |
|---|---|
| `/session-wrap` | Save decisions, learnings, and next steps before ending a session |

**Onboarding**
| Command | What it does |
|---|---|
| `/onboard` | Welcome a new PM or designer and guide them through tool access and first commands |
