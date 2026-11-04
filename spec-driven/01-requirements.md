# 01 · Requirements

Create `REQUIREMENTS.md` in the repository root. It owns WHAT the system must do. The repository is empty. Use only the notes below and my interview answers. Don't infer behavior. Anything the notes leave open goes under `## Open Questions`. Write requirements in plain language.

## Project notes

<<PROJECT_NOTES>>

## Required sections, in this order

### `## Required Requirement Inputs`

One line per field, `UNKNOWN` if unanswered: project purpose; users and actors; core workflows; data entities; external integrations; authentication and roles; regulatory or privacy constraints; target surfaces (web UI, APIs, background jobs).

### `## Functional Requirements`

Group them under `###` headings by capability. Format: `- **FR-1.1** The system MUST ...`, using MUST, MUST NOT, SHOULD, and MAY. Each requirement is one externally observable, independently testable behavior. Name the actor, action, response, and data where the notes give them. Include the validation, authorization, and failure behavior each workflow needs, and leave out implementation detail. If a missing fact would make a requirement untestable, ask it as an open question instead.

### `## Non-Functional Requirements`

Use `NFR-1.1` and so on, under the same rules. If none are stated, write `None stated`.

### `## Open Questions`

`- **OQ-1** ...`, limited to questions that change behavior, scope, or testability.

Save the file before the interview.

## Interview

Interview me one question at a time in plain language, waiting for each answer. Update `REQUIREMENTS.md` with the answers and remove only resolved questions. Preserve deferred items for steps 07 and 09.
