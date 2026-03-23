---
name: misinformation-disinformation-analysis
description: Detect distortion risks before they contaminate the analytic picture. Use when the evidence environment may include rumor, manipulation, or coordinated narrative activity.
---

# Misinformation and Disinformation Analysis

## Objective
Detect distortion risks before they contaminate the analytic picture.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The reporting environment may include rumor, recycled claims, or deliberate manipulation.
- Narrative activity itself may be part of the problem.
- The analyst needs to distinguish genuine signal from contaminated signal.

## Do Not Use When
- The evidence set is already tightly controlled and source-vetted.
- The task is broad intelligence synthesis with no distortion concern.
- The problem is purely internal reasoning rather than evidence contamination.

## Required Inputs
- Reporting set or narrative corpus
- Source provenance details
- Question or target claim set

## Helpful Inputs
- Posting or publication timeline
- Cross-platform propagation patterns
- Known incentives or adversary messaging goals

## Workflow
1. Identify the claims or narratives that matter to the question.
2. Trace origin, propagation path, and dependence across sources.
3. Assess whether the distortion appears accidental, opportunistic, or deliberate.
4. Separate contaminated claims from still-usable evidence.
5. Return the contamination risk and the safe analytic path forward.

## Templates To Reuse
- Use the source evaluation table, alternative comparison, and node-link minimum schema in [Templates](../../references/shared/templates.md).

## Quality Bar
- Origin tracing should distinguish first report from repeated amplification.
- The output should explain whether contamination affects the main judgment or only context.
- Usable evidence should be separated from suspect evidence.
- The rationale should name the likely distortion mechanism when possible.

## Common Failure Modes
- Treating repetition as corroboration.
- Calling a claim disinformation without evidence of deliberate intent.
- Discarding all reporting instead of isolating the contaminated strands.
- Ignoring the effect of manipulation on confidence.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Node Link Analysis](../node-link-analysis/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md), [Psychological Cascades Analysis](../psychological-cascades-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Confidence Language](../../references/shared/confidence-language.md).
