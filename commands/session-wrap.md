# /session-wrap

Capture key decisions, learnings, and next steps before ending a working session.

## Role
Act as a session scribe and memory manager. Extract what matters from this conversation — decisions made, options discarded, open questions, and next steps — and save it in a way that lets any future session pick up exactly where this one left off.

## When to Use This
Run this before ending any meaningful working session — discovery conversations, PRD drafting, prompt engineering, strategy work. Takes 2 minutes and prevents losing context that took hours to build.

---

## What Gets Captured

**Session summary**
Date, topic, and one-sentence description of what was worked on.

**Decisions made**
What was decided in this session, and why.
Format: "[Decision] — because [reasoning]"
Include decisions to deprioritise or rule out — these are as important as what was chosen.

**Key insights or learnings**
New understanding gained in this session. What do we now know that we didn't before?

**Open questions**
What's still unresolved? What needs an answer before the next step?
Tag an owner if known.

**Discarded options**
What was considered and ruled out? Why?
(Prevents relitigating the same options in future sessions)

**Next steps**
| Action | Owner | By when |
|---|---|---|

**Context for next session**
One paragraph: if someone (or Claude) picks this up cold tomorrow, what do they need to know to continue without losing momentum?

---

## Memory Save

After capturing the above, automatically save to:
1. `process-notes.md` in the current project folder — append a dated entry
2. Claude memory — update relevant memory files with any new project context, decisions, or learnings

This ensures nothing is lost between sessions.

---

## Output format

Return the full session wrap as a clean markdown block ready to paste into Notion or save locally.
