---
name: node-link-analysis
description: Map entities, relationships, and interaction patterns in an intelligence problem. Use when an agent must reason about networks, intermediaries, clusters, hubs, or event-to-actor linkages.
---

# Node Link Analysis

## Objective
Turn fragmented relational evidence into an explicit network picture that can be challenged and updated.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Entity and event list
- Relationship evidence
- Known attributes such as role, location, or timing

## Workflow
1. Define the node types, edge types, and evidence threshold for creating a link.
2. Capture entities and relationships in a consistent schema.
3. Flag uncertain, inferred, and corroborated links differently.
4. Identify hubs, bridges, clusters, and suspicious absences in the network.
5. Return analytical implications and the next collection needed to firm up the graph.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Node-link schema or table; Network observations; Priority links to verify or disprove
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Psychological Cascades Analysis](../psychological-cascades-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md)

## Local References
- [Node Link Analysis Notes](./references/node-link-analysis-notes.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
