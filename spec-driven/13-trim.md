# 13 · Trim dependencies

Cut the dependencies the build picked up, using Trim Reaper (https://github.com/jmanico/trim-reaper). Use a local checkout, or read its readme from GitHub.

1. Run its assessment-only prompt and show me the prioritized plan. Wait until I approve a scope.
2. Apply its shared instruction, then run passes 1 through 7 within that scope. Retain the authentication, cryptography, parsing, and security libraries selected in `ARCHITECTURE.md` unless a reviewed replacement preserves their protections.
3. If a pass removes or replaces a technology, update `ARCHITECTURE.md` and the affected security rules and public source references in `SECURITY.md` in the same change.
4. Finish with pass 8 and its report, giving measured counts only.
