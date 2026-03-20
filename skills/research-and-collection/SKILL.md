---
name: research-and-collection
description: Plan and execute intelligence-focused research and collection passes. Use when an agent must find relevant reporting, log sources, separate collection from analysis, or prepare an evidence set for later evaluation.
---

# Research and Collection

## Objective
Build a disciplined evidence set without collapsing collection and judgment into the same step.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Scoped intelligence question
- Collection constraints
- Existing leads, sources, or seed reporting

## Workflow
1. Translate the question into collection objectives and prioritized subtopics.
2. Capture each source with provenance, access date, and why it may matter.
3. Separate observed facts from source claims and analyst notes.
4. Flag missing, stale, single-source, or low-access reporting as provisional.
5. Hand off a clean evidence ledger for source evaluation and synthesis.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Prioritized evidence ledger; Source log; Collection notes and unresolved gaps
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md)
- Downstream: [Source Evaluation](../source-evaluation/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Source Evaluation](../source-evaluation/SKILL.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md)

## Shared Doctrine
Read and apply: [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
