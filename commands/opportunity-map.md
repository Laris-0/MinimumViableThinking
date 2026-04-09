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

Return:
1. Outcome statement (refined)
2. Opportunity map (table format)
3. Prioritised opportunity with reasoning
4. Solution ideas for top opportunity
5. Assumption map
6. Recommended first experiment
