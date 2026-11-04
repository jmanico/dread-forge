# 01 · Requirements

Create `REQUIREMENTS.md` in the repository root. It owns WHAT the system must do. The repository is empty, and the notes below are the only source of truth. Don't infer behavior. Anything the notes leave open goes under `## Open Questions`. Write requirement statements in ASD-STE100 Simplified Technical English.

## Project notes

<<PROJECT_NOTES>>

## Required sections, in this order

### `## Required Requirement Inputs`

One line per field, filled only from the notes, `UNKNOWN` otherwise: project purpose; users and actors; core workflows; data entities; external integrations; authentication and roles; regulatory or privacy constraints; target surfaces (web, mobile, API, background jobs).

### `## Functional Requirements`

Group them under `###` headings by capability. Format: `- **FR-1.1** The system MUST ...`, using MUST, MUST NOT, SHOULD, and MAY. Each requirement is one externally observable, independently testable behavior. Name the actor, action, response, and data where the notes give them. Include the validation, authorization, and failure behavior each workflow needs, and leave out implementation detail. If a missing fact would make a requirement untestable, ask it as an open question instead.

### `## Non-Functional Requirements`

Only what the notes state, as `NFR-1.1` and so on, under the same rules. If the notes state none, write `None stated`.

### `## Open Questions`

`- **OQ-1** ...`, limited to questions that change behavior, scope, or testability.

Save the file and reply with only its contents.

## `## Interview`

When done, please interview me one question at time as if I was a 12 year old to resolve all open questions. When the interview is done, delete the open questions and update REQUIREMENTS.md.
