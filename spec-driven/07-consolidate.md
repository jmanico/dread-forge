# 07 · Consolidate the specs

Review the six spec files so each owns exactly one domain, nothing is duplicated, and nothing is lost. Move every rule to the file that owns it. Don't modify `REQUIREMENT_TEMPLATE.md`, `logo.svg`, or `design/preview.html`. Keep the `## Third-party libraries` section of `AGENTS.md` word for word.

## Ownership

- `REQUIREMENTS.md`: what the system must do, including externally observable validation, authorization, and failure behavior.
- `DESIGN.md`: brand, logo, tokens, typography, layout, components, accessibility, and security-relevant interaction and rendering.
- `ARCHITECTURE.md`: components, interfaces, data flow, trust boundaries, and the stack with its rationale.
- `SECURITY.md`: secure-coding rules, controls, enforcement, and open security decisions. Every security control is written here.
- `SECURITY_EVENTS.md`: which security events are recorded, their contract, and their ledger status.
- `AGENTS.md`: agent operating rules and commands. No system behavior or architecture.

When content fits more than one file, controls go to `SECURITY.md`, event definitions go to `SECURITY_EVENTS.md`, and observable product behavior stays in `REQUIREMENTS.md`.

## Procedure

1. **Inventory** every ID (`FR`, `NFR`, `OQ`, `DQ`, `AQ`, `DR`, `SC`, `OD`, `SEC`) and every unnumbered rule or claim, tagged with the file that owns it.
2. **Detect** duplicates, contradictions, and low-signal content such as filler, restated obvious points, and dead links. Keep all files as concise as possible without losing critical detail.
3. **Resolve.** After you move the owner's copy of each duplicate, remove the original and only keep the moved version. Delete low-signal content, and when you're unsure, keep it and list it in your summary. Settle a contradiction with the owning file when ownership is clear. Don't pick an interpretation just because it sounds more secure, and never reuse an ID.
4. **Verify.** Re-read all six files end to end. Confirm that nothing was dropped, that every reference resolves to a real entry, and that each file stands on its own.

## Interview

Collect every unresolved item in the six specs: open questions and decisions (`OQ`, `DQ`, `AQ`, `OD`), unresolved markers and placeholders, missing or provisional required inputs, and blocked rules or event rows awaiting a decision. Order them by dependency, with requirements and architecture before downstream choices.

Interview me one question at a time in plain language, waiting for each answer. Explain the choices and their consequences without assuming technical knowledge. Don't guess or answer for me. Add questions raised by an answer to the list. Continue until every open or unresolved item is answered or explicitly deferred by me. Update all spec files with the answers. When done, remove all the resolved open questions. Do not continue until all open questions are resolved and removed.

## Second pass

Repeat the consolidation procedure after the interview. If this exposes new questions, interview the user again and reconcile the answers in the owning files. Repeat the Verify step after any second-pass interview edits. Report what moved, what was deleted, which decisions were resolved, and what remains uncertain. Keep going until all open questions are resolved.
