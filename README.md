# Intelligence Skill Pack

This folder is the portable distribution artifact for the intelligence-analysis skill library. It is designed to be copied into another repository, mounted into a LangGraph runtime, or published as a standalone skill pack without bringing along the source workspace's planning files and seed notes.

## What It Is
This project is a modular skill library for autonomous intelligence-analysis agents. It packages topic discovery, question framing, collection, source evaluation, structured analytic techniques, writing skills, and LangGraph-oriented execution rules into a portable folder.

## Included
- `skills/`: all skill folders, including the router and leaf skills
- `references/shared/`: doctrine shared across skills
- `catalog/skills-map.md`: human-readable skill inventory
- `catalog/skill-taxonomy.json`: machine-readable routing and dependency metadata
- `catalog/langgraph-integration.md`: runtime expectations for autonomous execution
- `PACK_MANIFEST.json`: pack-level entrypoint and packaging metadata

## Entry Point
- Start with `skills/intelligence-analysis-router/` when the correct skill chain is not already known.
- Start with `skills/find-intelligence-topics/` when you need good intelligence topics before you have a specific question.

## What It Demonstrates
- Router-plus-leaf skill architecture for autonomous agents
- A shared analytical contract across topic discovery, analysis, and writing
- Portable packaging for LangGraph-style execution without user follow-up
- Machine-readable routing metadata in `catalog/skill-taxonomy.json`

## Runtime Contract
- Skills are designed for unattended execution.
- Skills should not ask the user clarifying questions.
- Skills should return `status`, `primary_output`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and optional `blocker_reason`.

## Quick Use
1. Load `catalog/skill-taxonomy.json`.
2. Start with `intelligence-analysis-router` or `find-intelligence-topics`.
3. Route follow-on steps from `recommended_next_skill`.
4. Persist `assumptions_used`, `missing_inputs`, and `confidence` in graph state.
5. Treat `blocked` as an operator-review or external-collection branch.

## Packaging Rule
Copy this folder as a unit. The skills depend on `references/shared/` and `catalog/skill-taxonomy.json`; copying only `skills/` is not sufficient.
