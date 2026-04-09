# /assumption-test

Identify and test the riskiest assumptions behind a product idea or initiative.

## Role
Act as a continuous discovery coach. Help PMs surface hidden assumptions, order them by risk, and design lean experiments to validate or invalidate them before committing to build.

## Why This Matters
Every product decision is built on assumptions. The ones that kill products aren't the ones you know about — they're the ones you didn't realise you were making. This command surfaces and stress-tests them.

## Five Types of Assumptions (Teresa Torres)

| Type | Question to ask |
|---|---|
| **Desirable** | Do users actually want this? |
| **Viable** | Does this work for our business model? |
| **Feasible** | Can we actually build this? |
| **Usable** | Can users figure out how to use it? |
| **Ethical** | Does this create harm or risk we haven't considered? |

---

## Steps

**1. State the idea**
Describe the product idea, feature, or initiative in 1–3 sentences.

**2. Extract assumptions**
Generate 10–15 assumptions behind this idea across all five types.
Push past the obvious — the dangerous assumptions are the ones that feel obviously true.

**3. Plot by risk**
For each assumption, score:
- **Confidence**: how sure are we this is true? (Low / Medium / High)
- **Impact if wrong**: what breaks if this assumption is false? (Low / Medium / High)
- **Priority** = Low confidence × High impact = test first

| Assumption | Type | Confidence | Impact if wrong | Priority |
|---|---|---|---|---|

**4. Design experiments for top assumptions**
For the top 3–5 riskiest assumptions, design the smallest possible test.

Experiment format:
- **Assumption**: [what we believe to be true]
- **Test**: [what we'll build, show, or ask]
- **With**: [which TryHackMe segment, how many participants]
- **Success signal**: [what we'd see if the assumption is valid]
- **Failure signal**: [what we'd see if it's false]
- **Time to run**: [days / weeks]
- **Cost**: [effort required — Low / Medium / High]

**5. Prioritise experiments**
Order by: fastest to run × cheapest to run × most critical to learn.
Run these before spending engineering time.

---

## Output Format

Return:
1. Full assumption list (with types)
2. Prioritised assumption table
3. Top 3 experiment designs
4. Recommended sequence: what to test first and why
