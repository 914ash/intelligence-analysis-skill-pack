---
name: evidence-gap-analysis
description: Make uncertainty explicit and convert it into collection priorities. Use when the current evidence base has consequential known unknowns.
---

# Evidence Gap Analysis

## Objective
Make uncertainty explicit and convert it into collection priorities.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The current evidence base supports partial analysis but still has consequential unknowns.
- The consumer needs to know what is missing and why it matters.
- The workflow needs collection priorities instead of generic caveats.

## Do Not Use When
- No meaningful evidence has been collected yet.
- The main task is to weigh competing hypotheses rather than expose unknowns.
- The gap list is already explicit and prioritized.

## Required Inputs
- Intelligence question or draft judgment
- Current evidence set
- Existing assumptions or confidence statement

## Helpful Inputs
- Consumer decision deadline
- Collection constraints
- Indicator list or prior gap assessments

## Workflow
1. List the known unknowns that materially affect the answer.
2. Distinguish between critical gaps, secondary gaps, and context gaps.
3. Explain how each gap affects confidence, scope, or the plausibility of alternatives.
4. Identify what evidence would close or narrow each gap.
5. Recommend collection moves that would most reduce uncertainty.
6. Return a ranked gap list with watch items and collection implications.

## Templates To Reuse
- Use the gap register and short update template in [Templates](../../references/shared/templates.md).

## Quality Bar
- Gaps should be stated as missing evidence, not generic uncertainty.
- Priorities should reflect analytic impact, not ease of collection.
- The output should connect gaps to the current confidence level.
- Low-value open questions should not dilute the critical list.

## Common Failure Modes
- Listing too many minor unknowns.
- Confusing disagreement with a true gap.
- Failing to say how a gap affects the judgment.
- Recommending collection with no reason it would change the analysis.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Downstream: [Research and Collection](../research-and-collection/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md), [Analysis of Competing Hypotheses](../analysis-of-competing-hypotheses/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
