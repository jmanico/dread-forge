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
  <a href="#related-projects">Related projects</a> ·
  <a href="LICENSE">MIT license</a>
</p>

---

Dread Forge is a collection of standalone prompts for building web applications and their APIs with a coding agent. Start with your project notes. Work through requirements, design, architecture, security rules, and threat modeling before turning the specs into GitHub issues and code.

The stack comes from your project's requirements and choices. Security rules come from public guidance for that stack. Later steps read the files earlier steps created, so the work carries across fresh agent sessions.

## Start forging

1. Clone this collection:

   ```sh
   git clone https://github.com/jmanico/dread-forge.git
   ```

2. Open **your target project's repository** in a coding agent with repository and web access. The backlog and build steps also need GitHub access.
3. Open [01 · Requirements](spec-driven/01-requirements.md), replace `<<PROJECT_NOTES>>` with your notes, and paste the prompt into the agent.
4. Follow the [step-by-step guide](spec-driven/README.md) for the full sequence, interviews, and files to commit.

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

Dread Forge is available under the [MIT License](LICENSE), with copyright held by Manicode Security. You may use, modify, distribute, and sell copies, including in commercial products, provided that you retain the copyright and permission notices in copies or substantial portions of the software. The license does not require public promotional credit for every commercial use.
