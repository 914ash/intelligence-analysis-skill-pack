---
name: psychological-cascades-analysis
description: Analyze how perception, rumor, emotion, and social reinforcement may amplify a security event or narrative. Use when crowd behavior, contagion effects, or belief cascades shape the analytic question.
---

# Psychological Cascades Analysis

## Objective
Model how beliefs and reactions spread, not just the initiating event.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Event or narrative
- Actor set
- Signals of amplification, fear, outrage, or imitation

## Workflow
1. Identify the triggering event or claim.
2. Map the channels and audiences through which reactions are spreading.
3. Separate direct effects from second-order amplification effects.
4. Assess how rumor, emotion, or identity dynamics may alter behavior.
5. Return implications for stability, escalation, or further information distortion.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Cascade model; Amplification drivers; Implications and watch indicators
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Formal vs Informal Problem Solving](../formal-vs-informal-problem-solving/SKILL.md), [Misinformation and Disinformation Analysis](../misinformation-disinformation-analysis/SKILL.md)
- Downstream: [Intelligence Analysis](../intelligence-analysis/SKILL.md), [Defend Analytic Conclusion](../defend-analytic-conclusion/SKILL.md)
- Companions: [Node Link Analysis](../node-link-analysis/SKILL.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Confidence Language](../../references/shared/confidence-language.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
