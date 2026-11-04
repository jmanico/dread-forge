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

Reply with a short summary of what moved, what was deleted, and what you kept but weren't sure about.

## `## Interview`

When done, please interview me one question at time as if I was a 12 year old to resolve all open questions. When the interview is done, delete the open questions and update DESIGN.md.

## `## Second Pass`

When done, run the consolidater and interview (if necessary) a second time. This is a critical and invasive operation that we need to get correct.

