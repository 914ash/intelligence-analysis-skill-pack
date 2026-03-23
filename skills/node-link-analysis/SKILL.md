---
name: node-link-analysis
description: Map entities, relationships, and interaction patterns in an intelligence problem. Use when an agent must reason about networks, intermediaries, clusters, hubs, or event-to-actor linkages.
---

# Node Link Analysis

## Objective
Turn fragmented relational evidence into an explicit network picture that can be challenged and updated.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The problem is about actors, intermediaries, transactions, or influence paths.
- Relationships matter as much as events or attributes.
- The workflow needs a structured graph or network view before synthesis.

## Do Not Use When
- The problem is primarily temporal or narrative rather than relational.
- There is not enough entity normalization to distinguish nodes cleanly.
- A simple list of actors is enough and no network reasoning is needed.

## Required Inputs
- Entity and event list
- Relationship evidence
- Known attributes such as role, location, or timing

## Helpful Inputs
- Alias table
- Confidence or provenance on each link
- Temporal sequencing notes

## Workflow
1. Define node types, edge types, and the evidence threshold for creating a link.
2. Normalize entities, aliases, and time references before building the graph.
3. Flag uncertain, inferred, and corroborated links differently.
4. Identify hubs, bridges, clusters, choke points, and suspicious absences.
5. Return the analytical implications and the next links that most need verification or disproof.

## Templates To Reuse
- Use the node-link minimum schema and alternative comparison in [Templates](../../references/shared/templates.md).
- Use the local working table in [Node Link Analysis Notes](./references/node-link-analysis-notes.md).

## Quality Bar
- Entity normalization should be explicit.
- Inferred links should be visually or textually distinct from observed links.
- The output should explain why network structure matters to the question.
- Priority follow-up should target the most consequential uncertain links.

## Common Failure Modes
- Merging distinct actors into one node.
- Presenting inferred edges as observed facts.
- Focusing on graph shape without analytic meaning.
- Ignoring time sequence when it matters to the relationship.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Psychological Cascades Analysis](../psychological-cascades-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md)

## Local References
- [Node Link Analysis Notes](./references/node-link-analysis-notes.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Templates](../../references/shared/templates.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md).
