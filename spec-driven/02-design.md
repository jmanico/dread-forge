# 02 · Design

Create `DESIGN.md`, `logo.svg`, and `design/preview.html` in the repository root. Read `REQUIREMENTS.md` first. It owns behavior and workflows, and nothing is built yet.

Use `UNKNOWN` for facts you weren't given, `TO BE DECIDED` for decisions not made yet, and `ASSUMPTION` for any inference the requirements don't support. Never invent values.

## Direction

Follow the `frontend-design` skill from https://github.com/anthropics/skills (`skills/frontend-design/SKILL.md`). Use the installed skill if there is one; otherwise read the file from a clone outside this repository. Work in its two passes. First write a brief: subject, audience, and the primary job of the main screens, drawn from the requirements. Then draft a token plan covering color, type, layout, and principles. Review that plan against the brief and the skill's list of generic defaults, and revise whatever would fit any product as well as this one. Record the brief and final design rationale in `## Overview`.

## DESIGN.md

- Follow the `@google/design.md` format: YAML front matter tokens, then the prose sections it defines, in its order. Put `## Open Questions` (`DQ-1`, `DQ-2`, ...) last. Run `npx @google/design.md lint DESIGN.md` and fix every error.
- Every foreground and background pair the design uses meets WCAG 2.2 AA: 4.5:1 for normal text, 3:1 for large text, and 3:1 for UI components, focus indicators, and meaningful graphics.
- Describe components without choosing a CSS framework.
- Cover the security-relevant interactions the requirements imply: how signed-in state shows, how destructive or privileged actions are confirmed, what error messages may reveal, and how user-supplied content is displayed.

## logo.svg

One simple mark that reads at 16 px and at full size, drawn in the DESIGN.md palette. Plain SVG with a `viewBox` and a `<title>`, using shapes and paths rather than text, with no scripts, event handlers, external references, or `<foreignObject>`.

## design/preview.html

One self-contained static page with no scripts, no external requests, and no framework. It shows the logo, the palette, the type scale, each component and its states, and the product's single most important screen built from realistic content in the requirements. Take screenshots at 390 px and 1440 px wide with whatever browser tool you have, critique them against the brief, and fix what's weak. If you can't take screenshots, say so.

Leave out directory maps, code beyond the preview page, deployment, speculative features, and security controls. Keep DESIGN.md compact.

## Interview

Interview me one question at a time in plain language, waiting for each answer. Update `DESIGN.md` with the answers and remove only resolved questions. Preserve deferred items for steps 07 and 09.
