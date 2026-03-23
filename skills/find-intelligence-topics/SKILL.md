---
name: find-intelligence-topics
description: Turn a broad mission area into a prioritized set of analyzable intelligence topics with rationale and next-step question seeds. Use when a team needs to decide what to analyze.
---

# Find Intelligence Topics

## Objective
Turn a broad mission area into a prioritized set of analyzable intelligence topics with rationale and next-step question seeds.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The mission area is broad and no specific question has been selected yet.
- The workflow needs topic discovery before question framing.
- The analyst must prioritize where to spend limited analytic attention.

## Do Not Use When
- A clear intelligence question already exists.
- The task is collection or synthesis on a chosen issue.
- The output needs only a brainstorming dump with no prioritization.

## Required Inputs
- Broad mission area, industry, or threat space
- Decision context or stakeholder need
- Any known constraints or priority themes

## Helpful Inputs
- Time horizon
- Geographic scope
- Known actors or trigger events

## Workflow
1. List plausible topic areas inside the mission space.
2. Filter for topics that are analyzable, consequential, and appropriately scoped.
3. Rank them by decision value, urgency, and expected tractability.
4. Provide one or more candidate intelligence questions for each top topic.
5. Return the top topics with rationale and suggested next skill routing.

## Templates To Reuse
- Use the topic triage card and intelligence question brief in [Templates](../../references/shared/templates.md).
- Use the local ranking table in [Topic Selection Heuristics](./references/topic-selection-heuristics.md).

## Quality Bar
- Topics should be specific enough to analyze.
- Prioritization should be tied to decision value.
- The output should make the next framing step obvious.
- Low-value or vague topics should be cut.

## Common Failure Modes
- Returning a generic brainstorm list.
- Choosing trendy topics with little decision value.
- Failing to explain prioritization.
- Leaving topics too broad to frame.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md)
- Companions: [Intelligence Analysis](../intelligence-analysis/SKILL.md)

## Local References
- [Topic Selection Heuristics](./references/topic-selection-heuristics.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Templates](../../references/shared/templates.md).
