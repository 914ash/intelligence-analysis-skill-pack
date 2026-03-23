# Intelligence Skill Pack

This repository is a portable skill library for intelligence analysis and intelligence writing. It is designed to be copied into another repo, used directly by a human-guided agent, or mounted into a workflow runtime without dragging along the larger workspace that produced it.

## What It Includes
- `skills/`: the router plus leaf skills for framing, collection, analysis, structured techniques, and writing
- `references/shared/`: common doctrine, templates, style notes, and source-derived tradecraft references
- `references/source-docs/`: Markdown copies of source material worth shipping with the pack
- `catalog/skills-map.md`: human-readable skill inventory
- `catalog/skill-taxonomy.json`: machine-readable routing and dependency metadata
- `catalog/langgraph-integration.md`: optional workflow-engine guidance
- `PACK_MANIFEST.json`: pack-level entrypoint and packaging metadata

## Where To Start
- Start with `skills/intelligence-analysis-router/` when the right skill chain is not already obvious.
- Start with `skills/find-intelligence-topics/` when you have a mission area but not yet a good intelligence question.
- Jump directly into a leaf skill when the task is already well scoped.

## What The Pack Demonstrates
- Router-plus-leaf skill architecture for analytical work
- Shared doctrine across discovery, collection, evaluation, synthesis, and writing
- Portable references and templates that keep the skill files leaner than a monolithic playbook
- A public-safe artifact that is readable without knowing the parent workspace

## Source Foundations
The pack now pulls more explicitly from the sources listed in `Suggested Refs.txt`, especially:
- ODNI ICD 203 analytic standards
- CIS guidance on estimative probability, analytic confidence, and SAT usage
- The US Government structured analytic techniques primer mirrored as `references/source-docs/us-government-structured-analytic-techniques-primer-2009.md`
- Public intelligence and newsletter writing signals from The Cipher Brief, Semafor Flagship, and The Intelligence Shop

See `references/shared/source-foundations.md` for the source-to-reference crosswalk.

## Human-Guided And Workflow-Engine Use
The default reading of the pack is now method first: each skill explains how to execute the tradecraft, what artifact to produce, and which references to load. If you embed the pack in a workflow engine, keep the existing outer envelope from `PACK_MANIFEST.json` and `catalog/langgraph-integration.md`.

## Quick Use
1. Review `catalog/skills-map.md` or `catalog/skill-taxonomy.json`.
2. Pick the router or the smallest leaf skill that matches the task.
3. Load the shared references the skill points to before drafting the artifact.
4. Preserve assumptions, gaps, confidence, and next-step routing if the skill is used inside a larger workflow.

## Packaging Rule
Copy this folder as a unit. The skills depend on `references/shared/` and `catalog/skill-taxonomy.json`; copying only `skills/` is not sufficient.
