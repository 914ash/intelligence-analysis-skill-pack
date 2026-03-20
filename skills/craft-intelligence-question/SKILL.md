---
name: craft-intelligence-question
description: Turn a vague prompt into a scoped intelligence question with decision relevance, actors, timeframe, and information needs. Use when the request is broad, underspecified, or missing the key judgment to answer.
---

# Craft Intelligence Question

## Objective
Convert a loose request into a precise intelligence question and a supporting question set.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Original prompt
- Known decision-maker or consumer
- Timeframe, geography, and actor hints if known

## Workflow
1. Identify the decision or judgment the user actually needs.
2. Define the primary actor, geography, timeframe, and outcome of concern.
3. Rewrite the task as one principal intelligence question plus a short list of supporting questions.
4. Surface hidden assumptions and any terms that need operational definitions.
5. State what evidence would count as a strong answer or disconfirming signal.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Primary intelligence question; Supporting questions; Scope boundaries and assumptions; Initial indicators or information needs
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md), [Find Intelligence Topics](../find-intelligence-topics/SKILL.md)
- Downstream: [Research and Collection](../research-and-collection/SKILL.md), [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Evidence Ledger Template](../../references/shared/evidence-ledger-template.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
