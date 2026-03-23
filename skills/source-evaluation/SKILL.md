---
name: source-evaluation
description: Score reporting discipline before any substantive judgment leans on it. Use when source quality and claim quality need to be made explicit.
---

# Source Evaluation

## Objective
Score reporting discipline before any substantive judgment leans on it.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- Reporting exists but has not been graded for reliability and credibility.
- The analyst needs to separate strong signals from weak or contaminated inputs.
- A later analytic method depends on source-quality weighting.

## Do Not Use When
- There is no evidence set yet.
- The need is to generate alternative hypotheses rather than grade reporting.
- The product already contains a clear, defensible source-quality assessment.

## Required Inputs
- Evidence ledger or reporting set
- Source descriptors or provenance details
- Intelligence question or use case

## Helpful Inputs
- Existing reliability history for repeat sources
- Corroborating or contradictory reporting
- Collection context explaining access, motive, and timing

## Workflow
1. Separate source reliability from information credibility.
2. Evaluate access, track record, motive, timeliness, and transmission chain.
3. Identify corroboration, contradiction, dependence, and circular sourcing.
4. Assign working grades with a brief reason for each high-impact item.
5. Flag information that is usable only with heavy caveats or not usable at all.
6. Return what evidence is safe to lean on and what needs downgrading.

## Templates To Reuse
- Use the source evaluation table and evidence ledger row in [Templates](../../references/shared/templates.md).

## Quality Bar
- High-impact claims should have explicit grading rationale.
- Recycled reporting should be recognized as dependent, not independent.
- The grading should be reusable by downstream methods.
- Uncertainty about the grade should be stated rather than hidden.

## Common Failure Modes
- Treating a trusted source as reliable on every topic.
- Confusing plausibility with corroboration.
- Missing shared-source reporting chains.
- Ignoring timeliness.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md), [Node Link Analysis](../node-link-analysis/SKILL.md)
- Companions: [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Admiralty Scale Quick Reference](../../references/shared/admiralty-scale.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
