---
name: delphi-method
description: Facilitate a Delphi-style expert consensus workflow with structured rounds, controlled feedback, and convergence checks. Use when an agent needs to synthesize multiple expert views on a complex intelligence question.
---

# Delphi Method

## Objective
Run a repeatable expert-consensus process without losing question discipline or transparency.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The question benefits from structured expert elicitation rather than only document review.
- The workflow needs convergence and dissent tracking across rounds.
- The analyst must preserve anonymity and controlled feedback in a consensus process.

## Do Not Use When
- A single-analyst evidence synthesis is sufficient.
- There is no panel, proxy panel, or expert-judgment input to structure.
- The task requires a fast one-pass answer rather than iterative convergence.

## Required Inputs
- Problem statement
- Panel criteria or expert list
- Consensus threshold and round constraints

## Helpful Inputs
- Questionnaire draft
- Stopping rule
- Rules for anonymity and feedback summaries

## Workflow
1. Define the research question, panel criteria, round design, and stopping rule.
2. Draft round-one prompts and specify the response format.
3. Aggregate round results with controlled, anonymized feedback.
4. Track convergence, disagreement, attrition, and persistent dissent across rounds.
5. Stop when the preset convergence threshold is met or when the round limit is reached.
6. Return the consensus judgment, dissent areas, and residual uncertainties.

## Templates To Reuse
- Use the Delphi round summary and key judgments block in [Templates](../../references/shared/templates.md).
- Use the local round design prompts in [Delphi Method Notes](./references/delphi-method-notes.md).

## Quality Bar
- The question design should stay stable enough to support convergence.
- Feedback should be anonymized and controlled rather than argumentative.
- Consensus threshold and stopping rule should be explicit.
- Dissent should be preserved, not washed away.

## Common Failure Modes
- Changing the question too much between rounds.
- Treating apparent silence as consensus.
- Hiding dissent behind aggregate wording.
- Running too many rounds with no convergence rule.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Key Judgments Writing](../key-judgments-writing/SKILL.md), [Intelligence Writing](../intelligence-writing/SKILL.md)
- Companions: [Estimative Probability](../estimative-probability/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Local References
- [Delphi Method Notes](./references/delphi-method-notes.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Structured Technique Selection](../../references/shared/structured-technique-selection.md), [Structured Analytic Techniques Primer](../../references/shared/structured-analytic-techniques-primer.md), [Confidence Language](../../references/shared/confidence-language.md), [Templates](../../references/shared/templates.md).
