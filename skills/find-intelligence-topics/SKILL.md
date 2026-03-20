---
name: find-intelligence-topics
description: Generate, rank, and refine promising intelligence topics from a mission area, watchlist, or decision space. Use when an agent needs to decide what questions are worth analyzing before scoping a specific intelligence question.
---

# Find Intelligence Topics

## Objective
Turn a broad mission area into a prioritized set of analyzable intelligence topics with rationale and next-step question seeds.

## Autonomous Execution
- Do not ask the user clarifying questions during autonomous runs.
- If context is missing, state assumptions and continue with the safest reversible path.
- Return missing information in `missing_inputs` instead of prompting a human.
- Set `status` to `blocked` only when the task is impossible or unsafe without external input.

## Required Inputs
- Mission area, broad domain, or watchlist
- Known consumer priorities, decisions, or risk concerns if available
- Known geography, timeframe, actor set, or collection constraints if available

## Workflow
1. Identify the decision space, threat space, or monitoring need that makes the topic worth analyzing.
2. Generate candidate topics anchored to concrete actors, capabilities, events, intentions, vulnerabilities, or anomalies.
3. Filter out topics that are too vague, timeless, or disconnected from a decision-maker's needs.
4. Rank the remaining topics by importance, timeliness, tractability, and likely evidence availability.
5. Convert the strongest topics into short intelligence-question seeds and recommend the next skill.

## Output Contract
- `status`: `complete`, `partial`, or `blocked`
- `primary_output`: Ranked topic shortlist; topic-selection rationale; candidate intelligence-question seeds; recommended first topic
- `assumptions_used`: assumptions required to proceed without user follow-up
- `missing_inputs`: missing but non-blocking context
- `confidence`: confidence in the artifact or routing decision
- `recommended_next_skill`: next skill folder name or `null`
- `blocker_reason`: present only when `status` is `blocked`

## Cross-Links
- Upstream: [Intelligence Analysis Router](../intelligence-analysis-router/SKILL.md)
- Downstream: [Craft Intelligence Question](../craft-intelligence-question/SKILL.md), [Research and Collection](../research-and-collection/SKILL.md), [Evidence Gap Analysis](../evidence-gap-analysis/SKILL.md)
- Companions: [Critical Thinking](../critical-thinking/SKILL.md)

## Local References
- [Topic Selection Heuristics](./references/topic-selection-heuristics.md)

## Shared Doctrine
Read and apply: [Analytical Contract](../../references/shared/analytical-contract.md), [Workflow Sequencing](../../references/shared/workflow-sequencing.md), [Autonomous Execution Policy](../../references/shared/autonomous-execution-policy.md).
