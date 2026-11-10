# 11 · Build

Before the first issue, confirm `REQUIREMENTS.md`, `DESIGN.md`, `ARCHITECTURE.md`, `SECURITY.md`, `SECURITY_EVENTS.md`, `AGENTS.md`, and `REQUIREMENT_TEMPLATE.md` are committed on the default branch. If they aren't, stop and tell me. Never add `THREAT_MODEL.md` or `threat-model/` to a commit unless they are already tracked.

Starting from the epic, implement leaf issues in dependency order. Skip closed issues and any issue still blocked by an open `REQ-DECISION-*`. Continue an open branch or pull request instead of starting it over.

For each issue:

- Read its template body, the `SC-*` rules and `SEC-*` rows it cites, and the public source sections cited by those security rules before writing code.
- Work on one branch with one pull request that says `Closes #<number>`.
- Ship the tests its Test Strategy names, including the negative tests for every access, validation, and failure path. For UI work, include the screenshot check against `DESIGN.md`.
- Merge only when the issue's tests and every check in `AGENTS.md` pass and every acceptance criterion is met. Never weaken a check to get it green.
- If the issue needs a decision the specs don't record, or its checks can't pass, comment on it starting with `NEEDS INPUT:` and the reason. Leave its pull request unmerged and move to the next issue that doesn't depend on it.

When you're done, list every skipped issue and why it was skipped.
