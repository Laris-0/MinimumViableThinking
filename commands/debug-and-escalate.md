# /debug-and-escalate

Reproduce a bug, find its root cause, quantify user impact, and produce a Notion incident doc and Jira ticket.

## Role
Act as a debugging specialist with a PM lens. Investigate systematically, propose a minimal fix, and produce documentation that connects the technical issue to user impact.

## Rules
- Never claim to have created or updated Notion or Jira — produce drafts only
- Propose the minimal fix — avoid large refactors
- Always include a regression test plan
- Redact secrets, tokens, or credentials from logs before including them
- Quantify user impact where possible — which segments, how many users, what frequency
- Ask for clarification at intake if reproduction steps are unclear

---

## Workflow

1. **Intake** — gather: bug description, reproduction steps, environment, logs, expected vs. actual behaviour, when it was first seen
2. **Reproduce** — confirm reliable reproduction
3. **Localise** — narrow down where in the system the failure occurs
4. **Diagnose** — identify root cause, not just symptoms
5. **Quantify impact** — which segments affected? How many users? How critical is the flow?
6. **Propose fix** — minimal, targeted change with reasoning
7. **Draft docs** — Notion incident report + Jira ticket

---

## Notion Incident / Bug Report Draft

**Title**
[Bug] — [Short description] — [Date]

**Summary**
One paragraph: what broke, when, what the user impact is.

**User Impact**
- Which TryHackMe segments are affected? (Segment 1–5, B2B)
- Estimated number of affected users (if determinable via Amplitude)
- Which user flow is broken?
- Severity: Critical / High / Medium / Low
- Is there a workaround available?

**Reproduction Steps**
Numbered, specific steps to reliably reproduce the issue.

**Expected Behaviour**
What should happen.

**Actual Behaviour**
What happens instead. Include sanitised logs or screenshots.

**Root Cause**
What caused this? Be specific — not "a bug in the code" but the exact mechanism.

**Fix Proposed**
What change resolves it and why this is the right fix.

**Timeline**
- When introduced (if known)
- When discovered
- When resolved / ETA

---

## Jira Ticket Draft

**Title**
Fix: [short description]

**Priority**
P1 Blocker / P2 High / P3 Medium — based on user impact

**Context**
What broke, which users are affected, and why it matters.

**Root Cause**
From investigation above.

**Proposed Fix**
Specific, minimal change required.

**Acceptance Criteria**
- [ ] Bug no longer reproducible following reproduction steps
- [ ] No regression in [adjacent flows]
- [ ] Regression test added to prevent recurrence
- [ ] Amplitude confirms affected metric has recovered (if applicable)

**Regression Test Plan**
Steps to verify the fix didn't break adjacent functionality.

**References**
Notion incident doc, Amplitude dashboard, related tickets, logs.
