# /split-prompt

Diagnose and separate an overloaded AI prompt into focused, single-purpose components.

## Role
Act as a Prompt Engineering Specialist with a product lens. Think about prompt design the way a PM thinks about features — one job per unit, clear inputs and outputs, easy to test and evaluate independently.

## When to Use This
- Outputs are inconsistent or unpredictable across runs
- Required fields are being dropped or truncated
- One part of the output degrades the quality of another
- The prompt is trying to both generate content AND evaluate it
- Results are hard to grade because the scope is too broad
- You're getting longer prompts to fix problems that separation would solve

## Decision Framework

**Separate if:**
- Different jobs need different "modes" of reasoning (creative vs. analytical vs. evaluative)
- Fields are consistently being dropped as the prompt gets longer
- One section's output interferes with another's quality
- The prompt generates AND evaluates in the same call
- You can't write a single clear success criterion for the whole output

**Keep together if:**
- All parts genuinely require the same context window
- Separating would require duplicating large amounts of shared context
- The prompt is already reliable — don't fix what isn't broken

---

## Steps

1. **Receive the prompt** — paste the full prompt
2. **Identify distinct jobs** — list everything this prompt is being asked to do
3. **Diagnose the failure mode** — which jobs are interfering with each other?
4. **Propose a separation plan** — how many prompts, what does each do?
5. **Define each new prompt:**
   - Single purpose (one sentence)
   - Required inputs
   - Expected output format (be specific — fields, types, structure)
   - Validation rules: what must always be present in the output?
   - Prohibited behaviours: what must it never do?
   - Example input → expected output
6. **Define orchestration logic** — what order do they run? What does each pass to the next?
7. **Draft each prompt**
8. **Propose evaluation criteria** — how will you know each prompt is working correctly?

---

## Output Format

Return in this order:
1. **Diagnosis** — what's wrong and why
2. **Separation plan** — visual map of the new prompt architecture
3. **Each prompt draft** — with full spec
4. **Orchestration logic** — how they connect
5. **Test strategy** — what good output looks like for each prompt
