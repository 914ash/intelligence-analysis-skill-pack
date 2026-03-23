---
name: craft-intelligence-question
description: Convert a loose request into a precise intelligence question and a supporting question set. Use when the starting request is broad or underspecified.
---

# Craft Intelligence Question

## Objective
Convert a loose request into a precise intelligence question and a supporting question set.

## Autonomous Execution
- Use this skill as a method guide first; keep the tradecraft artifact separate from any outer workflow envelope.
- If context is missing, record the assumption, keep facts, inferences, assumptions, and gaps distinct, and continue on the safest reversible path.
- When the skill is embedded in a workflow engine, preserve `status`, `assumptions_used`, `missing_inputs`, `confidence`, `recommended_next_skill`, and `blocker_reason` only when blocked.

## Use When
- The initial request is broad, vague, or mixed across several problems.
- The workflow needs a question precise enough to guide collection and analysis.
- Scope control matters because mission creep is likely.

## Do Not Use When
- The question is already tightly framed and accepted.
- The task is to gather sources, not refine the analytic ask.
- The request is actually a writing task rather than an intelligence question.

## Required Inputs
- Initial topic, problem, or request
- Decision context or mission need
- Scope limits if known

## Helpful Inputs
- Time horizon
- Consumer or stakeholder type
- Known entities, geography, or event trigger

## Workflow
1. Identify the decision need or operational purpose behind the request.
2. Narrow the subject, actor, geography, and timeframe.
3. Decide whether the core question is descriptive, explanatory, predictive, or warning-oriented.
4. Draft supporting sub-questions that decompose the problem.
5. Remove wording that is normative, assumptive, or too broad to answer.
6. Return the primary intelligence question with scope notes and support questions.

## Templates To Reuse
- Use the intelligence question brief and topic triage card in [Templates](../../references/shared/templates.md).

## Quality Bar
- The main question should name actor, issue, and timeframe where possible.
- Support questions should decompose the problem rather than restate it.
- The wording should not presuppose the answer.
- The scope should be narrow enough to guide collection choices.

## Common Failure Modes
- Embedding assumptions in the question.
- Asking several questions at once.
- Making the question so broad that collection has no stop point.
- Forcing a specific answer shape through wording.

## Output Contract
- `status`: `complete` when the skill can deliver its artifact, `partial` when it can advance but key context is missing, `blocked` only when the task cannot safely proceed.
- `primary_output`: the primary artifact described below.
- `assumptions_used`: explicit assumptions carried to keep the workflow moving.
- `missing_inputs`: the highest-value missing context, evidence, or constraints.
- `confidence`: a concise confidence statement tied to evidence quality and scope fit.
- `recommended_next_skill`: the best next skill in the pack, or `null` if the workflow can stop here.
- `blocker_reason`: include only when `status` is `blocked`.

## Cross-Links
- Upstream: [Find Intelligence Topics](../find-intelligence-topics/SKILL.md), [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Research and Collection](../research-and-collection/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Intelligence Analysis](../intelligence-analysis/SKILL.md)
- Companions: [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md), [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Analytic Standards](../../references/shared/analytic-standards.md), [Tradecraft Foundations](../../references/shared/tradecraft-foundations.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Templates](../../references/shared/templates.md).
