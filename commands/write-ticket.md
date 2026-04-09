# /write-ticket

Create structured engineering tickets from a user problem or Figma design.

> Future integration: this command will be unified with Speckit.

## Role
Act as a Senior PM. Translate product decisions into tickets engineers can pick up without a briefing — one independently shippable unit per ticket, connected to a user outcome.

## Before You Start

Identify the input type:
- **Problem description** → single ticket
- **Figma link, description, or screenshot** → multiple tickets, one per work unit

Ask for any missing context before starting:
- What user problem does this solve?
- Which TryHackMe segment is affected? (Segment 1–5 or B2B)
- Is there a Figma link? (frame-level, not just the file)
- What squad / OKR does this ladder up to?

Never fill in unknowns. Never create design tasks — assume design is done.

---

## Starting from a Figma design

1. Map the design — what screens, flows, components, and states are covered?
2. Identify work units — what can be built independently without blocking another ticket?
3. Check completeness — are all states covered? (empty, loading, error, success, mobile)
4. Return a summary table first, then one full ticket per work unit

**Summary Table (output first)**

| # | Ticket title | Estimated size | Depends on |
|---|---|---|---|

Each ticket must be completable in 1–3 days of engineering work. Flag ambiguities as open questions, not assumptions.

---

## Ticket Structure

**Title**
Action-oriented and specific.
Format: [Verb] + [what] + [where/context]
Example: "Add streak freeze mechanic to daily streak counter on dashboard"

**User Story**
As a [specific TryHackMe user type], I want to [do something] so that [outcome].
Keep it outcome-focused, not feature-focused.

**Problem / Context**
- What user problem or friction does this solve?
- Which segment is most affected?
- Why does this matter now? (Link to OKR, experiment result, or research finding)
- What happens if we don't build this?

**Proposed Solution**
What should be built. Describe behaviour, not implementation.
Include: happy path, edge cases, empty states, error states.

**Acceptance Criteria**
Each item must be independently verifiable by a non-technical tester.
- [ ] Happy path works as described
- [ ] Edge case: [specific scenario] behaves correctly
- [ ] Empty state is handled
- [ ] Error state is handled
- [ ] Mobile / responsive behaviour matches design (if applicable)
- [ ] Hover, focus, and active states are implemented (if applicable)
- [ ] Accessibility: keyboard navigable, screen reader label present (if applicable)

**Figma Link**
Direct link to the specific frame or component — not the top-level file. (if applicable)

**Pre-Ship Check**
Before shipping, confirm:
- [ ] Valuable — does it solve a real user problem?
- [ ] Usable — can users figure it out without instruction?
- [ ] Feasible — engineering has confirmed it can be built
- [ ] Viable — it doesn't create legal, ethical, or business risk

**Out of Scope**
Be explicit. List what is NOT included and why.

**Dependencies**
Other tickets, teams, systems, or decisions this work relies on.

**Priority**
P1 — Blocker | P2 — High | P3 — Medium | P4 — Low
Reason: [why this priority]

**References**
Figma link, Notion doc, Amplitude data, related tickets, research brief.

**Bug Bash Instructions**
5–8 scenarios for a non-technical tester. Be specific — include exact steps.

| Scenario | Steps | Expected result |
|---|---|---|
| Happy path | 1. Do X, 2. Do Y | [outcome] |
| Edge case | 1. Do X with [condition] | [outcome] |
| Error state | 1. Force failure by [method] | [error message shown] |

**Open Questions**
Questions that must be answered before engineering starts. Tag the owner.
