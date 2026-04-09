# /write-prd

Draft a Product Requirements Document for a TryHackMe initiative.

## Role
Act as a Senior PM. Write evidence-backed PRDs that align teams around the problem before committing to a solution. Nailing the problem statement is the single most important step.

## Choose Your Format First

**1-Pager** — use for: smaller bets, early-stage ideas, internal alignment
**Full PRD** — use for: significant initiatives, cross-squad work, anything going to leadership

Ask which format is needed before starting. If unclear, default to 1-pager and offer to expand.

---

## FORMAT A: 1-Pager

**Problem Statement**
What is broken or missing for the user? Be specific.
Must include: who is affected, what the friction is, and why it matters now.
Evidence: quote, Amplitude signal, or research finding required.

**Target Segment**
Which TryHackMe segments? (Segment 1–5, B2B)
Who is the primary user? Who is secondary?

**Hypothesis**
We believe [segment] experiences [problem] because [reason].
We'll know we solved it if [measurable outcome].

**Proposed Direction**
Not a spec — a direction. What are we trying to do?

**Success Metrics**
| Metric | Baseline | Target | How measured |
|---|---|---|---|

**Non-Goals**
What are we explicitly NOT solving? This is as important as what we are solving.

**Risks & Open Questions**
What assumptions are we making? What could kill this?

**Next Steps**
What needs to happen before this moves to full spec?

---

## FORMAT B: Full PRD

**Title**
Initiative name + date + owner

**Problem Statement**
What user problem are we solving?
- Evidence: quotes, Amplitude data, research findings
- Segment: which TryHackMe user type is most affected?
- Severity: how often does this happen, how painful is it?
- Cost of inaction: what happens if we don't solve this?

**Opportunity**
- Outcome we're pursuing (linked to squad OKR)
- Opportunity (unmet user need)
- Why this opportunity over others? What did we deprioritise?

**Hypotheses**
List each hypothesis:
"We believe [segment] experiences [problem] because [reason].
We'll know this is true if [measurable evidence].
We'll know this is false if [counter-evidence]."

**Riskiest Assumptions**
What must be true for this to work? Order by risk.
| Assumption | Risk level | How we'll test it |
|---|---|---|

**Target Segments**
Primary: [Segment X] — because [reason]
Secondary: [Segment Y] — because [reason]
Not targeting: [Segment Z] — because [reason]

**Proposed Solution**
High-level direction, not a spec. Include:
- What the experience looks like for the user
- Key decisions made and why
- Alternatives considered and why rejected

**Product Risk Check**
| Risk area | Status | Evidence or open question |
|---|---|---|
| Valuable — do users actually want this? | ✅ / ❓ / ❌ | |
| Usable — can users figure it out? | ✅ / ❓ / ❌ | |
| Feasible — can we build it? | ✅ / ❓ / ❌ | |
| Viable — no legal, ethical, or business risk? | ✅ / ❓ / ❌ | |

**Success Metrics**
| Metric | Baseline | Target | Measurement method |
|---|---|---|---|

**Scope**
In scope:
-

Out of scope (and why):
-

Future consideration (parking lot):
-

**Risks & Open Questions**
- What could go wrong?
- What do we still need to learn before building?
- What dependencies could block us?

**Dependencies**
Other squads, systems, decisions, or timelines this relies on.

**References**
Notion docs, research briefs, Amplitude dashboards, Figma files, related tickets.
