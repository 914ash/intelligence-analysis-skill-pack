# 2026-03-21 Skill Pack Deepening And Release Polish

## Goal
Deepen the intelligence skill pack so the skills read like usable agent guides rather than sparse routing stubs, while keeping the pack portable and public-safe.

## Accepted Assumptions
- Work stays inside this portable pack rather than the larger parent workspace.
- The pack should still support workflow-engine execution, but the skill prose should prioritize tradecraft guidance over automation boilerplate.
- Suggested sources are used as doctrine and style inputs, not as text to copy verbatim.

## Scope
- Expand shared references, templates, and source-derived doctrine.
- Refactor every `skills/*/SKILL.md` to add clearer guide rails, reusable templates, and better reference pointers.
- Update repo-level packaging and release-facing docs so the pack reads cleanly as a public artifact.

## Out Of Scope
- Building new runtime code, executors, or orchestration scripts.
- Creating new skills beyond the current pack inventory.
- Reworking the machine-readable taxonomy unless a content change requires it.

## Verification Commands
- `rg --files`
- `Get-Content .\\PACK_MANIFEST.json | ConvertFrom-Json > $null`
- `Get-Content .\\catalog\\skill-taxonomy.json | ConvertFrom-Json > $null`
- `git diff --stat`

## Open Risks
- Source-derived guidance is intentionally distilled, so future maintainers should revisit the cited sources if they want more opinionated doctrine.
- `PACK_MANIFEST.json` still exposes the existing runtime contract and may need a later schema-level refresh if consumers want a more explicit human-guided mode.

## Status
- [x] Audit repo structure and existing skill pattern
- [x] Expand shared references and templates
- [x] Refactor skill docs
- [x] Apply release polish to repo surface
- [x] Run validation and close the plan
