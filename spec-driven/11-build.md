# 11 · Build

Starting from the epic, implement leaf issues in dependency order. Skip any issue still blocked by an open `REQ-DECISION-*`.

For each issue:

- Read its template body, the `SC-*` rules and `SEC-*` rows it cites, and the public source sections cited by those security rules before writing code.
- Work on one branch with one pull request that says `Closes #<number>`.
- Ship the tests its Test Strategy names, including the negative tests for every access, validation, and failure path. For UI work, include the screenshot check against `DESIGN.md`.
- Merge only when the issue's tests and every check in `AGENTS.md` pass and every acceptance criterion is met. Never weaken a check to get it green.

When you're done, list every skipped issue and why it was skipped.
