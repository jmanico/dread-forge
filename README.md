<p align="center">
  <img src="logo.svg" alt="Dread Forge: a skull in amber flames above an iron anvil" width="180" height="180">
</p>

<h1 align="center">Dread Forge</h1>

<p align="center">
  <strong>From rough notes to reviewed specs and working code.</strong><br>
  Thirteen prompts for coding agents, with security built into the workflow.
</p>

<p align="center">
  <a href="spec-driven/README.md"><strong>Start the workflow</strong></a> ·
  <a href="#the-thirteen-steps">Explore the prompts</a> ·
  <a href="#related-projects">Related projects</a> ·
  <a href="LICENSE">MIT license</a>
</p>

---

Dread Forge is a collection of standalone prompts for building software with a coding agent. Start with your project notes. Work through requirements, design, architecture, security rules, and threat modeling before turning the specs into GitHub issues and code.

The stack comes from your project's requirements and choices. Security rules come from public guidance for that stack. Later steps read the files earlier steps created, so the work carries across fresh agent sessions.

## Start forging

1. Clone this collection:

   ```sh
   git clone https://github.com/jmanico/dread-forge.git
   ```

2. Open **your target project's repository** in a coding agent with repository and web access. The backlog and build steps also need GitHub access.
3. Open [01 · Requirements](spec-driven/01-requirements.md), replace `<<PROJECT_NOTES>>` with your notes, and paste the prompt into the agent.
4. Follow the [step-by-step guide](spec-driven/README.md). Run one prompt at a time, in order, in a fresh session at your target project's root. Fill in each prompt's placeholders before running it.

The prompts use public resources. No commercial prompt collection, private repository, or separate requirement-template download is needed; step 06 includes the template.

## The thirteen steps

### 01–06 · Shape the project

| Step | What it produces |
| --- | --- |
| [01 · Requirements](spec-driven/01-requirements.md) | `REQUIREMENTS.md` from your project notes |
| [02 · Design](spec-driven/02-design.md) | `DESIGN.md`, a logo, and an HTML design preview |
| [03 · Architecture](spec-driven/03-architecture.md) | `ARCHITECTURE.md`, with stack choices and toolchain commands |
| [04 · Secure-coding rules](spec-driven/04-security.md) | `SECURITY.md`, grounded in public guidance for the chosen stack |
| [05 · Security events](spec-driven/05-security-events.md) | `SECURITY_EVENTS.md`, using Dread Ledger |
| [06 · Agent instructions](spec-driven/06-agents.md) | `AGENTS.md` and the embedded `REQUIREMENT_TEMPLATE.md` |

### 07–10 · Review before building

| Step | What it does |
| --- | --- |
| [07 · Consolidate](spec-driven/07-consolidate.md) | Reconciles the six specs, interviews you about open questions, and checks them again |
| [08 · Threat model](spec-driven/08-threat-model.md) | Uses Grim Prompter to write `THREAT_MODEL.md` and update the specs |
| [09 · Resolve open items](spec-driven/09-decisions.md) | Records your decisions in the files that own them |
| [10 · Backlog](spec-driven/10-backlog.md) | Creates a GitHub epic and implementation issues |

**Run step 09 again after the backlog.** Reconcile the specs and issues before building. Unresolved decisions stay explicit; they are not guesses for the agent to fill in.

### 11–13 · Build and verify

| Step | What it does |
| --- | --- |
| [11 · Build](spec-driven/11-build.md) | Implements issues in dependency order, with tests and one pull request per issue |
| [12 · Logging audit](spec-driven/12-logging-audit.md) | Reviews and verifies security logging with Dread Ledger |
| [13 · Trim](spec-driven/13-trim.md) | Reviews dependencies and removes unnecessary ones with Trim Reaper |

Step 11 skips issues blocked by open decisions and requires the issue's tests, project checks, and acceptance criteria to pass before merging.

## What stays with your project

Commit the specs, agent instructions, requirement template, logo, and design preview to your target repository. These files give later sessions the same project context and rules.

The `threat-model/` run folder is private review material. Review it for sensitive details before committing it. See the [workflow guide](spec-driven/README.md#what-gets-committed) for the full handoff.

## Related projects

Dread Forge uses these open-source projects by Jim Manico. Each can also be used on its own:

| Project | Role in the forge |
| --- | --- |
| [Grim Prompter](https://github.com/jmanico/grim-prompter) | Threat modeling in step 08 |
| [Dread Ledger](https://github.com/jmanico/dread-ledger) | Security event planning in step 05 and logging verification in step 12 |
| [Trim Reaper](https://github.com/jmanico/trim-reaper) | Dependency policy in step 06 and dependency review in step 13 |

We recommend cloning all three alongside Dread Forge so your coding agent can read their prompts and references locally. Run these commands from the parent directory containing your `dread-forge` checkout:

```sh
git clone https://github.com/jmanico/grim-prompter.git
git clone https://github.com/jmanico/dread-ledger.git
git clone https://github.com/jmanico/trim-reaper.git
```

Keep these checkouts outside the application you are building. Tell your agent where they are in each session that uses them (steps 05, 06, 08, 12, and 13), and follow each project's README for usage and any agent-specific setup. If you already have a checkout, use that copy instead of cloning it again.

## Contributing

Issues and pull requests are welcome. Keep each prompt self-contained and written in plain, direct language. Check links, placeholders, and step references before submitting a change. This collection has no automated validator.

## About the author

Created by Jim Manico of [Manicode Security](https://manicode.com) and [manicode.ai](https://manicode.ai).

## License

[MIT](LICENSE). Copyright (c) 2026 Jim Manico.
