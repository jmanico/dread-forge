# Spec-Driven Bootstrap

Thirteen self-contained prompts that take a new web application and its APIs from rough notes to reviewed specs, a GitHub backlog, and working code. Paste them into your coding agent one at a time, in order, each in a fresh session opened at the project's repository root. Later steps read the project files created by earlier steps.

| Step | Writes | Uses |
| --- | --- | --- |
| [01 · Requirements](01-requirements.md) | `REQUIREMENTS.md` | your notes |
| [02 · Design](02-design.md) | `DESIGN.md`, `logo.svg`, `design/preview.html` | public [`frontend-design` skill](https://github.com/anthropics/skills) |
| [03 · Architecture](03-architecture.md) | `ARCHITECTURE.md` | requirements and your stack choices |
| [04 · Secure-coding rules](04-security.md) | `SECURITY.md` | [Node.js security guide](https://nodejs.org/en/learn/getting-started/security-best-practices), [OWASP Node.js cheat sheet](https://cheatsheetseries.owasp.org/cheatsheets/Nodejs_Security_Cheat_Sheet.html) |
| [05 · Security events](05-security-events.md) | `SECURITY_EVENTS.md` | [Dread Ledger](https://github.com/jmanico/dread-ledger) |
| [06 · Agent instructions](06-agents.md) | `AGENTS.md`, `REQUIREMENT_TEMPLATE.md` | inline template and [Trim Reaper](https://github.com/jmanico/trim-reaper) policy |
| [07 · Consolidate](07-consolidate.md) | reconciled specs and recorded decisions | your interview answers |
| [08 · Threat model](08-threat-model.md) | `THREAT_MODEL.md`, spec updates | [Grim Prompter](https://github.com/jmanico/grim-prompter), DEEP web/API |
| [09 · Resolve open items](09-decisions.md) | answers in the owning files | you |
| [10 · Backlog](10-backlog.md) | GitHub epic and issues | |
| 09 again | reconciled specs and issues | you |
| [11 · Build](11-build.md) | code, one pull request per issue | |
| [12 · Logging audit](12-logging-audit.md) | verified security logging | Dread Ledger |
| [13 · Trim](13-trim.md) | a smaller dependency tree | Trim Reaper |

Before you paste a step, fill in its placeholders. Step 01 takes `<<PROJECT_NOTES>>`, step 03 takes `<<STACK_CHOICES_OR_NONE>>` and `<<ARCHITECTURE_NOTES_OR_NONE>>`, and step 04 takes `<<SECURITY_NOTES_OR_NONE>>`. Steps 01–05 each end with an interview to resolve open questions. Steps 07 and 09 handle remaining or newly raised questions. Run step 09 again after the backlog to reconcile the specs and issues before building.

## Stack and security

Step 03 chooses the stack from your requirements and explicit choices, verifies versions against official documentation, and records the toolchain commands. Unconfirmed choices stay proposed until resolved in an interview. Step 04 derives project security rules from public guidance for that stack, including the official Node.js guide and OWASP Node.js cheat sheet when Node.js is used.

## Setup

Step 06 includes the requirement template and saves it as `REQUIREMENT_TEMPLATE.md` in your project for later steps.

Steps 05, 06, 08, 12, and 13 use the [related projects](../README.md#related-projects). Step 02 uses the public `frontend-design` skill. Keep these checkouts outside your application repository. Use a coding agent with repository and web access, plus GitHub access for the backlog and pull requests.

## What gets committed

All the generated spec files, `AGENTS.md`, `REQUIREMENT_TEMPLATE.md`, `logo.svg`, and `design/preview.html` belong in your project repository, so later sessions read the same rules. The `threat-model/` run folder is private review material. Read it for sensitive details before committing it.
