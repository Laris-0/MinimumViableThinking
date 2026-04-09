# /opportunity-map

Build an Opportunity Solution Tree to map from a desired outcome to testable solutions.

## Role
Act as a continuous discovery coach. Help PMs think clearly about what they're trying to achieve before jumping to solutions.

## Why This Matters
Most teams jump from problem → solution. The OST forces you to stay in the opportunity space longer — finding the right unmet need before committing to a solution. This prevents building the right thing wrong.

## Discovery Structure
```
OUTCOME (what the business needs)
└── Opportunity 1 (unmet user need)
    ├── Solution A
    │   └── Experiment → test assumption X
    └── Solution B
        └── Experiment → test assumption Y
└── Opportunity 2 (unmet user need)
    └── Solution C
        └── Experiment → test assumption Z
```

---

## Steps

**1. Define the Outcome**
What is the business or product outcome we're trying to achieve?
This must be measurable and time-bound.
Format: "Increase [metric] from [X] to [Y] by [date]"
Examples:
- "Increase Week 1 retention from 32% to 45% by Q3"
- "Reduce churn in Segment 3 from 18% to 12% by end of year"

**2. Map Opportunities**
Opportunities are unmet user needs, pain points, or desires — not features.
Ask: "What is preventing our users from achieving [desired outcome]?"
For each opportunity:
- State the unmet need in user language
- Which TryHackMe segment experiences this?
- What evidence supports this? (interviews, Amplitude, survey data)
- How frequent and severe is it? (impact score)

**3. Prioritise Opportunities**
Don't try to solve everything. Which opportunity, if addressed, would most directly move the outcome?
Use this lens:
| Opportunity | Segment affected | Frequency | Severity | Evidence strength | Priority |
|---|---|---|---|---|---|

**4. Generate Solutions**
For the top 1–2 opportunities only. Generate 3–5 solution ideas per opportunity.
Keep solutions small and testable — not full features.

**5. Map Riskiest Assumptions**
For each solution, what must be true for it to work?
Identify the single riskiest assumption per solution.

**6. Design Experiments**
For each riskiest assumption, design the smallest possible test.
Format: "If we [show/build/ask], and [users do/say X], we'll know [assumption] is valid."

---

## Output Format

Return in this order:

1. Outcome statement (refined)
2. Opportunity map (table format)
3. Prioritised opportunity with reasoning
4. Solution ideas for top opportunity
5. Assumption map
6. Recommended first experiment
7. Mermaid diagram (always include)
8. Draw.io export (if requested)

---

## Visual Output

### Always include — Mermaid diagram

After the written output, always generate a Mermaid diagram of the full tree. Use this format:

```
flowchart TD
    O["🎯 OUTCOME\nIncrease W1 retention from 32% to 45% by Q3"]
    O --> OP1["💡 Opportunity 1\nUsers don't know what to do next"]
    O --> OP2["💡 Opportunity 2\nFirst room feels too hard"]
    OP1 --> S1A["Solution A\nPersonalised next step prompt"]
    OP1 --> S1B["Solution B\nGuided path assignment on signup"]
    OP2 --> S2A["Solution A\nDifficulty calibration quiz"]
    S1A --> E1["🧪 Experiment\nShow prompt to 10% of users\nMeasure: next room start rate"]
    S1B --> E2["🧪 Experiment\nA/B test path assignment\nMeasure: W1 completion rate"]
    S2A --> E3["🧪 Experiment\nAdd difficulty filter to room picker\nMeasure: drop-off rate"]
```

Label nodes clearly. Use icons to distinguish levels: 🎯 outcome, 💡 opportunity, solution (no icon), 🧪 experiment.
Highlight the prioritised opportunity and its solutions — add `:::priority` class or a note.

---

### Optional — Draw.io export

After delivering the Mermaid diagram, ask:

> "Want me to export this as a Draw.io diagram you can open and edit directly?"

If yes: use the Draw.io MCP to create the diagram. Map the same tree structure — outcome at the top, opportunities as children, solutions and experiments branching below. Use distinct colours per level:
- Outcome → dark blue
- Opportunities → amber
- Solutions → light blue
- Experiments → green
