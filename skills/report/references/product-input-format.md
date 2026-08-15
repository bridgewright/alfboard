# Product Input Document Format

This document carries field evidence to the product team. It is not a product requirements document and must not prescribe a complete solution.

## Required structure

```text
# Product Input: Evidence from the {customer} Deployment
Audience, purpose, and interview base

## 1. Principal Field Signal
## 2. Pain-Point and Need Map
## 3. Evidence by Need
## 4. Cross-Cutting Product Considerations
## 5. Evidence to Confirm and Track
```

## Method

- Lead with the one or two signals that matter most and explain why they are material.
- Group repeated signals by stable tags so evidence can be compared across deployments.
- For each need, describe the observed event, frequency, affected role, current workaround, consequence, and relevant product surface.
- State design conditions, edge cases, dependencies, and failure risks without writing a feature specification on behalf of the product owner.
- Preserve interview quotations or concrete events as evidence.
- Carry every unresolved material question into the final section.

## Product surfaces

Use a clear English label such as knowledge retrieval, rule evaluation, system action, conversation and clarification, human handoff, security and privacy, analytics and reporting, measurement, knowledge authoring, channel, or multilingual support.

Retain these aggregation tags when supported by the discovery record:

| Tag | Meaning |
| --- | --- |
| `action_task` | Execute a customer or operational action |
| `reask_context` | Gather missing context before answering or acting |
| `knowledge_authoring` | Create and maintain usable knowledge |
| `voc_distribution` | Return field evidence to other teams |
| `metric_redefine` | Improve or balance the success measure |
| `handoff_quality` | Improve human escalation and context transfer |
| `multilingual` | Support additional languages |
| `small_team` | Reduce setup burden for a small operating team |

Every material statement must trace to `product_gaps`, `bottlenecks`, `integration`, `metrics`, or a clearly labeled assumption.
