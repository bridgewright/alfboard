# Executive Deployment Brief Format

Write for the customer executive who sponsors the deployment. The document must support a decision, not merely summarize interviews.

## Writing standard

- State the recommendation and principal condition first.
- Begin each section with one clear message sentence.
- Use complete, concise, formal English.
- Explain technical terms at first use and avoid unexplained abbreviations.
- Support material claims with interview evidence, a number, or an explicit assumption.
- Label missing evidence as requiring confirmation.
- Do not use footnotes to hide a material qualification.

## Required structure

```text
# Deployment Brief: {customer} ({industry})
Executive audience, date, and interview evidence

## 1. Executive Recommendation
## 2. Operating Baseline
## 3. Bottleneck Diagnosis
## 4. Automation Candidates and Priority
## 5. Technical and Organizational Prerequisites
## 6. Indicative Delivery Economics
## 7. Expansion Opportunities
## Decisions and Evidence Required
```

### Executive recommendation

Connect the current operating burden, the highest-value bounded deployment, the principal technical or organizational condition, and the recommended sequence. Do not repeat section headings as a list.

### Operating baseline

Quantify volume, channel mix, team structure, handling time, and workflow ownership where evidence exists. Use a table for workflow mix. Unknown figures remain explicit.

### Bottleneck diagnosis

Group observed events into a small number of causal bottlenecks. Connect each bottleneck to frequency, handling time, rework, customer consequence, and the reason it has not already been automated. Include short attributed interview evidence.

### Automation candidates and priority

Compare candidates by volume, time per case, standardization, integration complexity, expected impact, and evidence quality. Distinguish knowledge retrieval, rule evaluation, and system action. A high-impact candidate with an unavailable interface belongs in a later phase rather than an immediate commitment.

### Prerequisites

For knowledge use cases, cover source availability, ownership, structure, maintenance, and preparation effort. For system actions, cover interface availability, documentation, authorization, security, failure recovery, and internal engineering capacity. Include change ownership and human escalation.

### Indicative economics

Show the assumptions, resource days, cost calculation, implementation range, recurring service assumption, and customer-side effort. Use `costing-assumptions.md`; never present an assumption as an agreed price.

### Expansion opportunities

Use only evidence in `product_gaps`, metrics, and open questions. Separate a credible adjacent opportunity from unsupported speculation.
