# 05 · Security events

Create `SECURITY_EVENTS.md` in the repository root: the security event ledger the build has to satisfy. Use Dread Ledger (https://github.com/jmanico/dread-ledger) from a local checkout, cloning it outside this repository if you need to. Read its `runbook.md`, `prompts/00-shared-instruction.md`, `prompts/01-assess.md`, and the files in `reference/`. Nothing is built yet, so run the assessment against the specifications instead of code.

Read `REQUIREMENTS.md`, `ARCHITECTURE.md`, `SECURITY.md`, and `DESIGN.md`. The only other file you may change is `SECURITY.md`, and only to add `OD-###` entries for decisions an owner has to make: destinations, retention, personal-data collection, and audit durability.

## Sections

1. `## Event Contract`: the project's event schema, following Dread Ledger's event contract. It covers stable event names, schema version, allowlisted fields with type and length limits, the trusted source of actor and tenant fields, outcome values, and the never-log list. Use the logger selected in `ARCHITECTURE.md`.
2. `## Ledger`: one row per Dread Ledger `SEC-###` ID, in checklist order. Each row records:
   - Disposition. Use `missing` for anything the specs make applicable, since nothing counts as covered until code passes verification. Use `not_applicable` only when the specs show the feature is absent, and `unavailable_signal` for everything else.
   - The requirement or component that triggers the event.
   - The proposed event name and fields.
   - The consumer.
   - The wave (0 to 4).

   Add project-specific events after the checklist rows as `SEC-APP-###`.
3. `## Open Decisions`: references to the `OD-###` entries you added to `SECURITY.md`. Don't repeat their text here.

Don't invent detectors, destinations, retention periods, or owners. Reply with the contents of `SECURITY_EVENTS.md`.

## `## Interview`

When done, please interview me one question at time as if I was a 12 year old to resolve all open questions. When the interview is done, delete the open questions and update SECURITY_EVENTS.md.