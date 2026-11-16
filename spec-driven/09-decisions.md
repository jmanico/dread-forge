# 09 · Resolve open items

Gate: this step does not end until every open item is resolved and its marker removed. Nothing may be deferred to a later step.

## Collect

Scan the repo for the items below. Skip `REQUIREMENT_TEMPLATE.md` (its placeholders are intentional), `threat-model/` (a fixed baseline), and text that only defines these markers (the SDD prompt files, status legends).
- `## Open Questions` entries and `OD-###` decisions
- `TO BE DECIDED`, `UNKNOWN`, `TBD`, `PROPOSED`, `DEFERRED`, `ASSUMPTION`, and leftover `<<...>>` or `{{...}}` placeholders
- Blank or provisional lines under `Required ... Inputs` or `Secure-Coding Inputs`
- `BLOCKED` rules in `SECURITY.md`, `unavailable_signal` rows in `SECURITY_EVENTS.md` waiting on an owner, and `THREAT_MODEL.md` findings that need a decision

Order the list most foundational first: requirements, then architecture, then everything downstream.

## Ask

Ask me one question at a time in plain language, and wait for each answer. Don't batch questions, guess, or answer for me. If an answer raises a new question, add it to the list.

If I can't answer an item yet, move it to the end of the list and come back to it. No item may be left open, marked deferred, or carried into a later step.

## Apply (after every item is answered)

- Write each answer into the file that owns it. Remove the markers it settles, the resolved open questions, and the `OD-###` entries. A `BLOCKED` rule becomes `ACTIVE` only when all of its dependencies are settled.
- Update everything downstream of a changed decision: `SC` rules, event rows, threat findings, acceptance criteria, coverage, and dependencies. If the stack changes, revisit the public sources and update the affected `SECURITY.md` rules and source references.
- `THREAT_MODEL.md`: record each decision against its `T-nnn` finding without re-analyzing the threat. Tell me when an answer changes a component, trust boundary, or data flow enough to need a new threat-model run.

## Verify

Run the Collect scan again. If it finds anything, return to Ask. Continue only when it finds nothing.
