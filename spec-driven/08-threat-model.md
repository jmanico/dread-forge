# 08 · Threat model the specs

Threat model the specifications with Grim Prompter (https://github.com/jmanico/grim-prompter), then fold its supported findings back into the specs. Use its installed `threat-model` skill if you have it; otherwise read `runbook.md` from a local checkout, cloning it outside this repository if needed. Don't ask questions, and don't analyze imagined code.

## Run it

Run DEEP mode (`MODE=deep`) for web and API surfaces. Use `deep/web/` for web applications and `deep/api/` for APIs; when both are present, cover both under the composition guide with explicit boundary ownership. Run all six stages, `00-scope-and-evidence.md` through `05-report-and-handoff.md`, in order for each applicable architecture. However the surfaces combine, finish with one report and one set of `T-nnn` IDs. Record absent surfaces as not applicable. Supply `REQUIREMENTS.md`, `ARCHITECTURE.md`, `SECURITY.md`, `SECURITY_EVENTS.md`, and `DESIGN.md` as the evidence. If any is missing, say so and stop. Nothing is implemented yet, so record that as an evidence gap instead of inventing code-level findings. A missing detail is a gap, not proof of a vulnerability. Follow the runbook's operating boundary for the whole run.

Once the run has finished, save its final report as `THREAT_MODEL.md` in the repository root, keeping the model, stable `T-nnn` IDs, evidence, conflicts, gaps, and coverage. Keep the run folder under `threat-model/`, because its JSON is the baseline for later change reviews. Review it for sensitive details before anyone commits it.

## Update the specs

The run is finished at this point, so you're outside its read-only boundary. Apply only the changes the evidence supports, each in the file that owns it:

- `SECURITY.md`: secure-coding rules and blocked security decisions.
- `REQUIREMENTS.md`: required product behavior.
- `ARCHITECTURE.md`: components, trust boundaries, data flows, enforcement placement, and the diagrams they affect.
- `DESIGN.md`: security-relevant interaction and rendering.
- `SECURITY_EVENTS.md`: events a threat needs for detection or investigation.

Keep each file's format and IDs, and link every change to the `T-nnn` that drove it. When a mitigation needs an unresolved decision, add an `OD-###` to `SECURITY.md` and keep the affected `SC-###` rule `BLOCKED`. Don't weaken existing requirements, treat planned controls as implemented, or add exploit instructions. When you're done, confirm that every reference you added resolves to a real entry and that no ID was reused.
