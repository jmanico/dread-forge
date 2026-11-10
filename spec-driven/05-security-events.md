# 05 · Security events

Create `SECURITY_EVENTS.md` in the repository root: the security event ledger the build has to satisfy. Use Dread Ledger (https://github.com/jmanico/dread-ledger) from a local checkout, cloning it outside this repository if you need to. Read its `runbook.md`, `prompts/00-shared-instruction.md`, `prompts/01-assess.md`, and the files in `reference/`. Nothing is built yet, so run the assessment against the specifications instead of code.

`SECURITY_EVENTS.md` is the agreed ledger location and is committed with the other specs. Keep secrets, real log content, and operational details out of it. Record the Dread Ledger commit you used at the top of the file.

Read `REQUIREMENTS.md`, `ARCHITECTURE.md`, `SECURITY.md`, and `DESIGN.md`. If any is missing, say so and stop. The only other file you may change is `SECURITY.md`, to record and resolve `OD-###` owner decisions about destinations, retention, personal-data collection, and audit durability, and update affected rules.

## Sections

1. `## Event Contract`: the project's event schema, following Dread Ledger's event contract. It covers stable event names, schema version, allowlisted fields with type and length limits, the trusted source of actor and tenant fields, outcome values, and the never-log list. Use the logger selected in `ARCHITECTURE.md`. If none is selected, record an `OD-###` instead of choosing one.
2. `## Ledger`: one row per Dread Ledger `SEC-###` ID, in checklist order. Each row records:
   - Disposition. Use `missing` for anything the specs make applicable, since nothing counts as covered until code passes verification. Use `not_applicable` only when the specs show the feature is absent, and `unavailable_signal` for everything else.
   - The requirement or component that triggers the event.
   - The proposed event name and fields.
   - The consumer.
   - The wave (0 to 4).

   Add project-specific events after the checklist rows as `SEC-APP-###`.
3. `## Open Decisions`: references to the `OD-###` entries you added to `SECURITY.md`. Don't repeat their text here.

Don't invent detectors, destinations, retention periods, or owners.

## Interview

Interview me one question at a time in plain language, waiting for each answer, until every open decision is answered or I defer it. Record answers in the owning sections of `SECURITY.md` and update affected rules and event rows. Replace resolved `OD-###` references with links to the recorded answers, then clear those entries. Preserve deferred decisions for steps 07 and 09.
