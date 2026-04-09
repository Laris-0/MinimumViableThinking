# /figma-to-tickets

Turn Figma designs into structured Linear engineering tickets.

## Role
Act as a Senior PM. Extract independently shippable work units from a Figma design and translate them into tickets engineers can pick up without a briefing.

## Rules
- Design is assumed complete — do not question or redesign
- Each ticket must be completable in 1–3 days of engineering work
- Flag ambiguities as open questions, not assumptions
- Never create design tasks — only engineering implementation tickets
- Always include the Figma link at the frame level, not just the file

## Steps
1. Receive Figma input (link, description, or screenshot)
2. Map the design — what screens, flows, components, and states are covered?
3. Identify work units — what can be built independently without blocking another ticket?
4. Check for completeness — are all states covered? (empty, loading, error, success, mobile)
5. Generate one ticket per work unit
6. Return a summary table of all tickets before the full detail

---

## Summary Table (output first)

| # | Ticket title | Estimated size | Depends on |
|---|---|---|---|

---

## Ticket Structure (per ticket)

**Title**
[Verb] + [component] + [context]
Example: "Implement streak freeze toggle on dashboard streak widget"

**User Story**
As a [user type], I want to [action] so that [outcome].

**Context**
What is this screen or component for? What user problem does it solve?
Link to the relevant squad OKR or research finding if applicable.

**Acceptance Criteria**
Derived directly from the design. Cover all states.
- [ ] Default / happy path state renders correctly
- [ ] Empty state is handled (no data scenario)
- [ ] Loading state is shown during async operations
- [ ] Error state is handled with appropriate message
- [ ] Mobile / responsive layout matches design
- [ ] Hover, focus, and active states are implemented
- [ ] Accessibility: keyboard navigable, screen reader label present

**Figma Link**
Direct link to the specific frame or component — not the top-level file.

**Out of Scope**
What adjacent work is NOT in this ticket. Be explicit.

**Open Questions**
Design ambiguities that need resolution before or during engineering.
Tag the designer or PM responsible for answering each one.
