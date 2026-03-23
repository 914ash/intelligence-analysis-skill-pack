---
name: intelligence-analysis
description: Synthesize evaluated reporting into structured intelligence judgments. Use when collection is in hand and the task is to integrate evidence, compare explanations, and produce findings.
---

# Intelligence Analysis

## Objective
Produce a traceable judgment from evaluated evidence rather than intuition alone, ensuring the reasoning can survive review and briefing.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- Collection and source evaluation are complete enough to support synthesis.
- The task is to produce a lead judgment, not just list facts.
- The consumer needs a best explanation, alternatives, and confidence.

## Do Not Use When
- The work is still mainly about gathering sources.
- The main need is to choose a technique rather than synthesize results.
- The task is purely editorial.

## Required Inputs
- Evaluated evidence set
- Scoped intelligence question
- Known alternatives or competing hypotheses

## Helpful Inputs
- Evidence ledger with reliability notes
- Prior baseline assessment
- Watch items or collection triggers

## Workflow
1. Restate the exact intelligence question, scope limits, and timeframe.
2. State the methodology used, including any structured technique already applied.
3. Organize the strongest evidence by relevance, quality, and diagnostic value.
4. Compare the lead explanation to at least one live alternative.
5. Separate facts, inferences, assumptions, and unresolved gaps.
6. Draft the lead judgment with confidence and explicit watch items.

## Templates To Reuse
- Use the long memo template, alternative comparison, and gap register in [Templates](../../references/shared/templates.md).

## Quality Bar
- Every major claim should be traceable to evidence quality.
- Alternatives should be serious, not token objections.
- The confidence statement should explain why confidence is not higher or lower.
- The output should make the next collection move clear.

## Common Failure Modes
- Repeating the evidence without making a judgment.
- Overstating confidence because several weak sources point the same way.
- Mixing assumptions into the fact base.
- Ignoring a plausible alternative.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Research and Collection](../research-and-collection/SKILL.md), [Source Evaluation](../source-evaluation/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md)
- Downstream: [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md), [Estimative Probability](../estimative-probability/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Source and Evidence Discipline](../../references/shared/source-and-evidence-discipline.md), [Confidence Language](../../references/shared/confidence-language.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Templates](../../references/shared/templates.md).
