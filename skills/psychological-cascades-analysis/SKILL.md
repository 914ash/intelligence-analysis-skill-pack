---
name: psychological-cascades-analysis
description: Model how beliefs, reactions, and triggers spread through a population or target set. Use when the question depends on cascade dynamics rather than a single event.
---

# Psychological Cascades Analysis

## Objective
Model how beliefs and reactions spread, not just the initiating event.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The problem is driven by rumor, fear, outrage, imitation, or narrative contagion.
- The analyst needs to understand second-order effects rather than only the trigger event.
- The likely impact depends on how reactions propagate across groups or networks.

## Do Not Use When
- The question is mainly about material capability rather than belief spread.
- There is no meaningful population, audience, or actor pathway to model.
- A simple event chronology is sufficient.

## Required Inputs
- Trigger event or narrative
- Relevant audience or actor groups
- Evidence on reactions, incentives, and transmission channels

## Helpful Inputs
- Media or messaging channels
- Node-link output
- Known barriers that may dampen the cascade

## Workflow
1. Define the initiating trigger and the relevant audience segments.
2. Map transmission channels, emotional levers, and amplification mechanisms.
3. Identify where reactions may accelerate, stall, or reverse.
4. Separate first-order effects from second-order and third-order effects.
5. Return the likely cascade path, dampeners, and collection indicators for early change detection.

## Templates To Reuse
- Use the psychological cascade chain and short update template in [Templates](../../references/shared/templates.md).

## Quality Bar
- The cascade model should include both amplifiers and brakes.
- Audience differences should be explicit.
- Second-order effects should be tied to evidence or clearly labeled assumptions.
- The output should identify observable indicators of spread or failure to spread.

## Common Failure Modes
- Treating all audiences as if they react the same way.
- Confusing speculation with evidenced pathways.
- Ignoring dampening forces.
- Stopping at the initial event instead of modeling propagation.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Node Link Analysis](../node-link-analysis/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
