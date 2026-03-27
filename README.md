# Intelligence Analysis Skill Pack

Intelligence Analysis Skill Pack is an experiment in teaching AI agents structured analytic tradecraft for intelligence-style analysis by packaging methods, references, and writing patterns gathered from public web sources into a reusable skill library.

- **Status:** Active public pack
- **Stack:** Markdown skill files, JSON routing metadata, bundled reference material
- **Problem:** Analytical workflows are often trapped inside one-off prompts or analyst memory instead of being captured as reusable, inspectable method.

## Why It Matters

- It treats analytical method as a product surface, not just supporting documentation.
- It separates routing, shared doctrine, and leaf skills so the pack can be reused across repos and runtimes.
- It keeps source foundations visible instead of burying them inside prompt text.

## What The Pack Includes

- `skills/`: router and leaf skills for framing, collection, evaluation, analysis, structured techniques, and writing
- `references/shared/`: doctrine, templates, style notes, and source-derived tradecraft references
- `references/source-docs/`: mirrored source material worth shipping with the pack
- `catalog/skills-map.md`: human-readable inventory
- `catalog/skill-taxonomy.json`: machine-readable routing metadata
- `PACK_MANIFEST.json`: pack-level packaging metadata

## Who It Is For

- Human-guided analysts who want reusable analytical workflows
- Agent builders who need a portable library of analytical methods
- Workflow-engine authors who want explicit routing and dependency metadata

## Quick Use

1. Review `catalog/skills-map.md` or `catalog/skill-taxonomy.json`.
2. Start with `skills/intelligence-analysis-router/` if the right skill chain is not obvious.
3. Load the shared references the selected skill points to.
4. Preserve assumptions, gaps, confidence, and next-step routing in the output artifact.

## Source Foundations

The pack draws from the source list in `Suggested Refs.txt`, including ODNI ICD 203 analytic standards, CIS guidance on probability and confidence language, the US Government structured analytic techniques primer, and public intelligence-writing signals such as The Cipher Brief and Semafor Flagship.

See `references/shared/source-foundations.md` for the source-to-reference crosswalk.

## Packaging Rule

Copy this repository as a unit. The skills depend on `references/shared/` and `catalog/skill-taxonomy.json`; copying only `skills/` is not sufficient.
