# 12 · Security logging audit

The application is built. Check its security logging against `SECURITY_EVENTS.md` with Dread Ledger (https://github.com/jmanico/dread-ledger), using a local checkout or one cloned outside this repository. Follow `prompts/00-shared-instruction.md` and `runbook.md` throughout.

1. Run `prompts/01-assess.md` against the code, using `SECURITY_EVENTS.md` as the prior ledger. Update every row's disposition from evidence. A row counts as `covered` only with an exact trigger in code, safe fields, a consumer, and a passing test.
2. If the assessment finds secrets or injection in existing logs, fix that first with `prompts/08-repair.md`.
3. If Wave 0 doesn't pass locally, run `prompts/02-foundation.md` before anything else.
4. Close gaps one wave at a time with prompts 03 through 06, but only for waves that still have `missing` rows. Each wave gets its own branch and pull request and finishes with `prompts/07-verify-and-rollout.md`.

Write the final dispositions and the Dread Ledger commit you used back into `SECURITY_EVENTS.md`. It is the agreed ledger location and is committed with the other specs, so keep secrets, real log content, and operational details out of it. Record owner decisions the ledger still needs as `OD-###` entries in `SECURITY.md`. Never deploy, read production logs, or send real notifications. Report each gate as PASS, FAIL, or NOT RUN, with evidence.
