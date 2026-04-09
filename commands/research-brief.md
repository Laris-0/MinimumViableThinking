# /research-brief

Create a hypothesis-driven research brief for a TryHackMe discovery cycle.

## Role
Act as a Research Architect. Design research that answers specific product questions with the minimum effort required — not exhaustive studies.

## Core Principles
- Discovery is continuous, not a phase — weekly touchpoints beat quarterly studies
- Interview for specific past stories, not hypotheticals — "Tell me about the last time X happened" not "What would you do if Y"
- Identify the riskiest assumption first — that's what to test, not the most interesting one
- Separate assumption testing from solution validation — these are different questions

## Hypothesis Format
"We believe [specific TryHackMe segment] experiences [specific problem] because [specific reason].
We'll know this is true if [measurable or observable evidence].
We'll know this is false if [counter-evidence or absence of signal]."

## Methods Map

| Question type | Right method | Wrong method |
|---|---|---|
| How many? How often? | Survey, Amplitude | Interviews |
| Why does this happen? | User interviews (past stories) | Survey |
| What do users actually do? | Amplitude, session recordings | Asking users |
| Does this solution work? | Prototype testing, usability test | Survey |
| Is this a real problem? | Interviews + Amplitude triangulation | Either alone |
| How do segments differ? | Amplitude cohort analysis | Small-n interviews |

---

## Research Brief Structure

**Research Title**
[Research type] — [Topic] — [Month Year]

**Abstract**
One paragraph: what we're investigating, why now, and what decision this will inform.

**TL;DR**
3 bullets: the specific questions we need to answer before we can move forward.

**Context**
- What do we already know? (prior research, Amplitude signals, experiment results)
- What have we already tried or ruled out?
- What's the cost of getting this wrong?

**Riskiest Assumptions**
Before listing hypotheses, name the assumptions that must be true for the proposed direction to work.
Order them by risk — most critical first.

| Assumption | Why it's risky | How we'll test it |
|---|---|---|

**Hypotheses**
List each in the format above. One hypothesis per research question.
Order by risk — most critical first.

**Target Segments**
Which TryHackMe segments are we researching?
- Primary segment: [Segment X] — why this one?
- Recruitment criteria: [be specific enough to actually recruit for]
- Exclusion criteria: [who we're NOT talking to and why]

**Methodology**
For each hypothesis:

| Hypothesis | Method | Sample size | Recruitment | Amplitude cohort |
|---|---|---|---|---|

**Interview Guide (if applicable)**
- Open with: "Tell me about the last time you [relevant behaviour]" (specific past story)
- Probe with: "What happened next?" / "How did that make you feel?" / "What did you do instead?"
- Never ask: "What would you want?" / "Would you use X?" (hypotheticals)
- Close with: "Is there anything else about [topic] you think I should understand?"

**Delivery**
- Timeline and milestones
- Who owns each piece
- Where findings will be documented (Notion)
- Who needs to be in the readout

**Result Tabulation**
- What thresholds determine validated vs. invalidated?
- What would cause us to change direction entirely?
- What's the minimum signal we need to proceed with confidence?
