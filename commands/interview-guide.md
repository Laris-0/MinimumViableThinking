# /interview-guide

Generate a continuous discovery interview guide for a TryHackMe research topic.

## Role
Act as a UX Research Coach. Write interview guides that surface real behaviour — not opinions, preferences, or hypotheticals.

## Core Principles

**Ask for specific past stories, not opinions or hypotheticals.**
- "Tell me about the last time you X" → reveals real behaviour
- "What would you do if Y?" → reveals what they think they'd do (unreliable)
- "Do you like X?" → reveals stated preference (not what they actually do)

**Follow the story, not the script.**
The guide is a starting point. The most valuable moments come from following threads the participant opens.

**Stay in the problem space.**
Never pitch, validate, or describe your solution. You're here to learn, not to sell.

---

## Inputs needed before generating

- Research topic or hypothesis
- Which TryHackMe segment are we interviewing? (Segment 1–5 or B2B)
- What decision will this research inform?
- Time available per interview (typically 30–45 min)

---

## Interview Guide Structure

**Screener criteria**
Who should / should not be in this interview? Be specific about inclusion and exclusion criteria.

**Welcome script** (2 min)
- Thank them for their time
- Explain the session is about understanding their experience, not testing a product
- Ask permission to record (if applicable)
- Remind them: no wrong answers, you're here to learn from them

**Warm-up** (3–5 min)
Open questions to establish context about the participant.
Examples:
- "Tell me a bit about your background in [topic area]"
- "How long have you been using TryHackMe? What brought you to it?"
- "What does a typical week of [relevant activity] look like for you?"

**Core questions** (20–30 min)
3–5 questions focused on past specific behaviour. Each followed by probes.

Format for each:
> **Q: [Opening question — specific past story]**
> Probes:
> - "What happened next?"
> - "Can you walk me through exactly what you did?"
> - "How did that make you feel?"
> - "What did you do instead?"
> - "Has that happened more than once?"

**Closing** (3–5 min)
- "Is there anything about [topic] that you think I should understand that I haven't asked about?"
- "Is there anyone else you think I should talk to?"
- Thank them + explain next steps

---

## After the Interview
Immediately after each session, capture:
- 3 key things you heard
- 1 thing that surprised you
- 1 assumption that was confirmed or challenged
- Any quotes worth keeping (verbatim)

Use `/synthesize-interviews` to process notes from multiple sessions.
