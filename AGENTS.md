# Dread Forge

This repository contains standalone prompts. Maintain the files by hand; there is no automated validator.

## What's here

Prompts for coding agents using public security guidance. `spec-driven/` is the bootstrap: thirteen self-contained prompts, one per `NN-name.md` file, and a README. Step 03 selects the stack from project requirements and choices; step 04 uses public security guidance; step 06 embeds the full requirement template and writes it into the user's project. The READMEs explain how to use it.

## Editing

- A step file gets pasted straight into an agent, so it holds the prompt and nothing else. Keep it short, and cut something before you add something.
- Placeholders look like `<<UPPER_SNAKE>>`, and every one is listed in `spec-driven/README.md`.
- When you add, remove, or renumber a step, update the README table and every "step NN" reference in the other files.
- Verify security guidance against public sources and official documentation for the selected versions. Distinguish project choices from source recommendations and repeat the review when the stack changes.
- Check version and support dates against the primary source, never memory.
- Nothing validates this folder automatically, so check links and step references by hand.

## Writing

- Write in a plain, direct, human voice: short sentences, concrete words, no marketing language.
- Commit messages and pull request bodies describe what changed and why. Leave out AI tools, models, co-author lines, and "generated with" taglines. The prompts themselves may name a tool they load, such as a skill or library.
