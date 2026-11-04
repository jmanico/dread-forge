# 07 · Consolidate the specs

Review the six spec files so each owns exactly one domain, nothing is duplicated, and nothing is lost. Move every rule to the file that owns it. Don't modify `REQUIREMENT_TEMPLATE.md`, `logo.svg`, or `design/preview.html`.

## Ownership

- `REQUIREMENTS.md`: what the system must do, including externally observable validation, authorization, and failure behavior.
- `DESIGN.md`: brand, logo, tokens, typography, layout, components, accessibility, and security-relevant interaction and rendering.
- `ARCHITECTURE.md`: components, interfaces, data flow, trust boundaries, and the stack with its rationale.
- `SECURITY.md`: secure-coding rules, controls, enforcement, and open security decisions. Every security control is written here.
- `SECURITY_EVENTS.md`: which security events are recorded, their contract, and their ledger status.
- `AGENTS.md`: agent operating rules and commands. No system behavior or architecture.

A file that doesn't own something links to the owner instead of restating it. When content fits more than one file, controls go to `SECURITY.md`, event definitions go to `SECURITY_EVENTS.md`, and observable product behavior stays in `REQUIREMENTS.md`.

## Procedure

1. **Inventory** every ID (`FR`, `NFR`, `OQ`, `DQ`, `AQ`, `DR`, `SC`, `OD`, `SEC`) and every unnumbered rule or claim, tagged with the file that owns it.
2. **Detect** duplicates, contradictions, and low-signal content such as filler, restated obvious points, and dead links.
3. **Resolve.** Keep the owner's copy of each duplicate and replace the others with a one-line reference at most. Delete low-signal content, and when you're unsure, keep it and list it in your summary. Settle a contradiction with the owning file when ownership is clear. Otherwise preserve the alternatives under a stable open-item ID in the owning file. Don't pick an interpretation just because it sounds more secure, and never reuse an ID.
4. **Verify.** Re-read all six files end to end. Confirm that nothing was dropped, that every reference resolves to a real entry, and that each file stands on its own.

## Interview

Collect every unresolved item in the six specs: open questions and decisions (`OQ`, `DQ`, `AQ`, `OD`), unresolved markers and placeholders, missing or provisional required inputs, and blocked rules or event rows awaiting a decision. Order them by dependency, with requirements and architecture before downstream choices.

Ask the user one question at a time, in plain language, and wait for each answer. Explain the choices and their consequences without assuming technical knowledge. Don't guess or answer for the user. Add questions raised by an answer to the list. Continue until every item is answered or explicitly deferred by the user.

Record each answer in the owning section, update references to point to that answer, then clear the resolved open-question or decision entry and only the markers the answer settles. Never reuse a cleared ID. Mark deferred items `DEFERRED` under a stable open-item ID in the owning file; preserve their context for step 09. Refresh dependent `SC` rules, event rows, acceptance criteria, and references. A `BLOCKED` rule becomes `ACTIVE` only when all its dependencies are settled. If a decision changes the stack, revisit the public sources and update affected rules and source references in `SECURITY.md`.

## Second pass

Repeat the consolidation procedure after the interview. If this exposes new questions, interview the user again and reconcile the answers in the owning files. Repeat the Verify step after any second-pass interview edits. Preserve unresolved items for step 09. Report what moved, what was deleted, which decisions were resolved, and what remains uncertain.
