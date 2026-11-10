# 09 · Resolve open items

Run this once after the threat model and again after the backlog exists. Run it again whenever later steps leave open items.

Collect every unresolved item in the repository. Skip `REQUIREMENT_TEMPLATE.md`, whose placeholders are intentional, and the `threat-model/` run folder, which is a fixed baseline. Look for:

- `## Open Questions` entries and `OD-###` decisions
- `TO BE DECIDED`, `UNKNOWN`, `TBD`, `PROPOSED`, `DEFERRED`, `ASSUMPTION`, and leftover `<<...>>` or `{{...}}` placeholders
- blank or provisional lines in any `Required ... Inputs` or `Secure-Coding Inputs` section
- `BLOCKED` rules in `SECURITY.md`, `unavailable_signal` rows in `SECURITY_EVENTS.md` that wait on an owner, and findings in `THREAT_MODEL.md` that need a decision
- once the backlog exists: open `REQ-DECISION-*` issues, issues marked blocked or ambiguous, and every `NEEDS INPUT:` comment

Put them in one list, most foundational first: requirements, then architecture, then everything downstream.

Ask me one question at a time in plain language, and wait for each answer. Don't batch questions, guess, or answer for me. If an answer raises a new question, add it to the list.

When every item is answered or I've deferred it:

- Write each answer into the file that owns it, remove the markers it settles, and clear the resolved open questions and `OD-###` entries. A `BLOCKED` rule becomes `ACTIVE` only when every dependency it has is settled.
- Mark deferred items `DEFERRED` under their decision ID, assigning the owning file's next open-item ID if they don't have one. They stay visible and block only the work that depends on them.
- Refresh everything downstream of a changed decision: `SC` rules, event rows, threat findings, acceptance criteria, coverage, and dependencies. If a decision changes the stack, revisit the public sources and update affected rules and source references in `SECURITY.md`.
- In `THREAT_MODEL.md`, record each decision against its `T-nnn` finding without re-analyzing the threat. Tell me when an answer changes a component, trust boundary, or data flow enough to need a new threat-model run.
- If the backlog exists, bring the epic and affected issues in line by creating, splitting, retiring, or re-parenting issues. Keep the ID scheme the existing issues use (`REQ-<CAPABILITY>-###` for leaves, `REQ-DECISION-###` for decisions) and never reuse an ID. Leaf bodies follow `REQUIREMENT_TEMPLATE.md`; other issues get short bodies that link spec IDs and issues. Pass bodies with `--body-file` from a temporary directory outside the repository. Retire an issue by closing it with a comment, never by deleting it. Then close each resolved `REQ-DECISION-*` issue with a comment recording the answer.
