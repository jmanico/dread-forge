# 10 · GitHub backlog

Turn the specification into one GitHub epic with implementation-ready sub-issues. Create the issues; don't stop for questions or leave work untracked.

Read `REQUIREMENTS.md`, `ARCHITECTURE.md`, `SECURITY.md`, `SECURITY_EVENTS.md`, `DESIGN.md`, `THREAT_MODEL.md`, `REQUIREMENT_TEMPLATE.md`, and `AGENTS.md` (for repository rules only). Each spec owns its domain. Never settle a conflict by reading order, and never invent scope.

## Plan

Before touching GitHub, build a coverage matrix and an acyclic dependency graph that map every `FR`, `NFR`, `SC`, `SEC`, `T`, architecture component, and design constraint to:

1. one root epic, `REQ-EPIC-001`
2. optional workstreams, `REQ-<CAPABILITY>-000`
3. decision issues for each unresolved item, `REQ-DECISION-010` onward; every implementation issue that depends on one links to it and stays blocked until it closes
4. leaf issues, `REQ-<CAPABILITY>-010` onward, titled like `[REQ-AUTH-010] Enforce authorization for account retrieval`

Nothing is left out. The coverage matrix goes in the epic, continuing in epic comments if it passes GitHub's body limit.

## Leaf issues

Each leaf implements one coherent behavior, control, endpoint, workflow, or data flow. It needs no undocumented decision, fits in two engineer-days and at most 1,500 changed lines, and includes its own tests, error handling, security, and accessibility. Its Given/When/Then criteria cover success, invalid input, unauthorized access, and failure, and it cites exact spec, `SC`, `SEC`, and `T` IDs. Split oversized or independently releasable work. Never create generic "build backend", "add security", cleanup, or testing-only issues.

Leaf bodies follow `REQUIREMENT_TEMPLATE.md` exactly, with every placeholder replaced and `N/A` used only where something truly doesn't apply. Epic, workstream, and decision issues get short bodies that link spec IDs and issues.

## Create them

Preflight: check `gh auth status`, confirm the target repository, look through open and closed issues for planning IDs already in use, and confirm the CLI or API supports sub-issues and dependency links. Reuse an issue only when its ID and scope both match. If an ID is taken by different scope, allocate the next free one and note the change.

Create in this order: epic, decisions and workstreams, leaves, sub-issue links, then dependency links and task lists. Pass every body with `--body-file`, writing the files to a temporary directory outside the repository. Capture and verify each issue number and URL, then replace placeholder links with the real ones. Use the sub-issues API if `gh issue create --parent` isn't available.

GitHub is the system of record, so don't create planning files in the repository or edit the specs. If an edit or link fails on an existing issue, comment on it starting with `NEEDS INPUT:` and the reason. If creating an issue fails, add a `NEEDS INPUT:` comment to the epic with its planning ID. Keep going after either kind of failure. Stop if the epic itself can't be created or the failure is systemic, such as authentication, permissions, or rate limits. Never delete issues, and never report an action as done without verifying it.

Reply with the epic URL and the counts of created, reused, and failed issues, giving each failure's planning ID.
