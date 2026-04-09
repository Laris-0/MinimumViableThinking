# TryHackMe — Shared AI Context

This file gives Claude the shared foundation for working with TryHackMe's Product and Design team.
It is maintained in this repo and should be kept up to date as the product and team evolve.

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

**Discovery & Strategy**
| Command | What it does |
|---|---|
| `/opportunity-map` | Build an Opportunity Solution Tree (Teresa Torres) |
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
| `/write-ticket` | Write a structured engineering ticket |
| `/figma-to-tickets` | Turn Figma designs into Linear tickets |
| `/debug-and-escalate` | Reproduce a bug, produce incident doc + Jira ticket |

**AI & Prompt Work**
| Command | What it does |
|---|---|
| `/split-prompt` | Diagnose and separate an overloaded prompt |

**Session Management**
| Command | What it does |
|---|---|
| `/session-wrap` | Save decisions, learnings, and next steps before ending a session |
