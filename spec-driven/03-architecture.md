# 03 · Architecture

Create `ARCHITECTURE.md` in the repository root. It owns HOW the system is built: components, boundaries, technology, and data flow. Read `REQUIREMENTS.md` and `DESIGN.md` first. If either is missing, say so and stop. Nothing is built yet.

## Stack

Choose the stack from the requirements and the explicit choices below. Verify version lines, support dates, and compatibility against official documentation. Record unavailable or incompatible choices as open questions.

- Stack choices: <<STACK_CHOICES_OR_NONE>>
- Architecture notes: <<ARCHITECTURE_NOTES_OR_NONE>>

Every package needs one line naming the requirement it serves and why the platform or an existing dependency cannot do the job. Start with the fewest services and data stores the requirements need.

## Rules

- Honor explicit requirements and choices. Flag conflicts rather than resolving them silently.
- Pick the simplest architecture that meets the requirements. Label any choice that isn't explicit or required as `PROPOSED`, with one sentence on why.
- Use `UNKNOWN` for missing facts and `TO BE DECIDED` for pending decisions. Never invent features, integrations, or scale targets.
- Record unresolved choices under `## Open Questions` as `AQ-1`, `AQ-2`, and so on.
- IDs are permanent. Never renumber or reuse one, because later files cite them.

## Sections

1. `## Required Architecture Inputs`, one line each: requirements and design sources; target surfaces (from `REQUIREMENTS.md`); runtime and deployment environment; server framework; client frameworks; API style; authentication and session model; authorization model; data store and expected scale; logging library or platform logger; security expectations (owned by `SECURITY.md`).
2. `## Stack`: every technology with its exact version line, requirement or explicit choice that justifies it, and status (`CONFIRMED` or `PROPOSED`).
3. `## Components and Flows`: a compact table of component, responsibility, business rules enforced, data owned, requirement IDs, and status (`SUPPORTED`, `PARTIALLY DEFINED`, or `TO BE DECIDED`). Follow it with the main data flows and every trust boundary, naming where authentication, authorization, and validation are enforced.
4. `## Dependency Rules`: `DR-1`, `DR-2`, ... covering explicit data ownership and one-way dependencies with no cycles. Keep business rules separate from transport, presentation, and vendor code.
5. `## Diagrams`: Mermaid diagrams only where they clarify something. Include one component and trust-boundary diagram, plus the main data flows if they help.
6. `## Toolchain`: install, build, type-check, test, and dependency-audit commands verified for the chosen stack. Mark inapplicable checks `N/A` with a reason and unresolved commands `TO BE DECIDED`.
7. `## Open Questions`.

No code, directory trees, class lists, or deployment topology. Name the enforcement points, but leave the detailed controls to `SECURITY.md`.

## Interview

Interview me one question at a time in plain language, waiting for each answer, until every open question is answered or I defer it. Update `ARCHITECTURE.md`, including confirmed choices, and remove only resolved questions. Preserve deferred items for steps 07 and 09.
