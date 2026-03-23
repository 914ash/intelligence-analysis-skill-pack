# Intelligence Skill Pack

This repository is a portable skill library for intelligence analysis and intelligence writing. It is designed to be copied into another repo, used directly by a human-guided agent, or mounted into a workflow runtime without dragging along the larger workspace that produced it.

## What We Built
- A router-plus-leaf skill pack for intelligence workflows, starting from question framing and collection, moving through evaluation and analysis, and ending in decision-oriented writing.
- A shared doctrine layer that keeps the skills aligned on evidence discipline, confidence language, and output structure.
- A portable pack surface that works both as human-readable guidance and as machine-routable workflow input through `catalog/skill-taxonomy.json` and `PACK_MANIFEST.json`.

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

## What The Skills Teach
- How to turn a vague mission area into a scoped intelligence question worth answering.
- How to separate collection, source grading, analysis, uncertainty handling, and writing instead of collapsing them into one fuzzy step.
- How to use structured methods such as ACH, Team A / Team B, TRACE, Delphi, and node-link analysis when a problem needs more rigor than informal reasoning.
- How to write outputs the way intelligence consumers actually use them: key judgments first, confidence stated clearly, and implications tied to evidence.

## Typical Workflow
1. Use the router to choose the smallest useful skill chain.
2. Frame the question with `find-intelligence-topics` or `craft-intelligence-question`.
3. Build and grade the evidence base with `research-and-collection` and `source-evaluation`.
4. Run core analysis or a structured technique such as ACH, TRACE, or node-link analysis.
5. Convert the result into usable prose with `intelligence-writing`, BLUF, key judgments, and title-writing skills.

## Source Foundations
The pack pulls from the source list in `Suggested Refs.txt` and turns those sources into reusable doctrine instead of burying them inside individual skill files. The main source families are:
- ODNI ICD 203 analytic standards
- CIS guidance on estimative probability, analytic confidence, and SAT usage
- The US Government structured analytic techniques primer mirrored as `references/source-docs/us-government-structured-analytic-techniques-primer-2009.md`
- Public intelligence and newsletter writing signals from The Cipher Brief, Semafor Flagship, and The Intelligence Shop

See `references/shared/source-foundations.md` for the source-to-reference crosswalk and which pack references were shaped by each source.

## Human-Guided And Workflow-Engine Use
The default reading of the pack is now method first: each skill explains how to execute the tradecraft, what artifact to produce, and which references to load. If you embed the pack in a workflow engine, keep the existing outer envelope from `PACK_MANIFEST.json` and `catalog/langgraph-integration.md`.

## Quick Use
1. Review `catalog/skills-map.md` or `catalog/skill-taxonomy.json`.
2. Pick the router or the smallest leaf skill that matches the task.
3. Load the shared references the skill points to before drafting the artifact.
4. Preserve assumptions, gaps, confidence, and next-step routing if the skill is used inside a larger workflow.

## Packaging Rule
Copy this folder as a unit. The skills depend on `references/shared/` and `catalog/skill-taxonomy.json`; copying only `skills/` is not sufficient.
