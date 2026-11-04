# 04 · Secure-coding rules

Create or replace `SECURITY.md` in the repository root. Change nothing else. This step writes implementation rules only: no threat modeling, risk scoring, or application code.

## Authority

Read `REQUIREMENTS.md` (behavior, data, integrations, compliance), `DESIGN.md` (interaction and rendering), and `ARCHITECTURE.md` (components, stack, trust boundaries). If any is missing, stop and report it. Then read the notes below and any existing `SECURITY.md`. Preserve existing rule IDs. Notes and sources cannot override confirmed project facts. Record conflicts, use `UNKNOWN` for missing facts and `TO BE DECIDED` for open choices, and don't ask questions or invent scope.

Security notes: <<SECURITY_NOTES_OR_NONE>>

## Read the public sources

- Node.js Security Best Practices: https://nodejs.org/en/learn/getting-started/security-best-practices
- OWASP Node.js Security Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/Nodejs_Security_Cheat_Sheet.html

Read both sources for Node.js components. For other runtimes, use their official security guidance and relevant OWASP cheat sheets. Use official documentation for the exact runtime, framework, and library versions in `ARCHITECTURE.md` to verify implementation details. Follow relevant OWASP cheat sheets for controls the two guides don't cover. If a required source is unavailable, record the gap and block the affected rules rather than guessing.

Apply guidance only to confirmed components. Check request and resource limits, event-loop blocking, input validation, output encoding, authentication, authorization, sessions, CSRF, errors, logging, dependencies, runtime permissions, prototype pollution, and unsafe code execution. Record why any relevant area is not applicable. Adapt examples to the chosen stack; an example package in a guide is not an approved dependency. Verify API names, defaults, support dates, and deprecated advice against current official documentation before using them.

## SECURITY.md

Use these four sections, in order, with compact entries and no wide tables.

### `## Secure-Coding Inputs`

List the documents read, confirmed components and versions, applicability decisions, and gaps or conflicts.

### `## Sources`

For each source, record its title, URL and section, retrieval date, version or revision when available, and the components it supports. Keep enough detail to find the guidance again.

### `## Secure-Coding Rules`

Turn applicable public guidance into project-specific `SC-###` rules. Cite the public source that supports each control. Distinguish source guidance from stricter project decisions; never attribute a project choice to a source that doesn't say it. Keep existing `SC-###` IDs whose meaning hasn't changed.

```markdown
**SC-001 — Short name**
- **Status:** ACTIVE
- **Rule:** One project-specific MUST or MUST NOT.
- **Enforcement:** The component or point that enforces it.
- **Evidence:** Project-document reference; source URL and section; project decision when applicable.
- **Verification:** An observable pass/fail check, including a negative test.
```

Don't copy source text wholesale, include secrets, or describe exploits. When evidence, applicability, or implementation details are unresolved, write a **BLOCKED** entry linked to its `OD-###` decision.

### `## Open Security Decisions`

For each `OD-###`: the missing fact or conflict, what would settle it, affected rules, and the documented owner (otherwise `UNKNOWN`). Write `None` only when nothing is open.

Before saving, check every rule for authority, provenance, applicability, and testability. Reply with the contents of `SECURITY.md`.

## `## Interview`

When done, please interview me one question at time as if I was a 12 year old to resolve all open questions. When the interview is done, delete the open questions and update SECURITY.md.
