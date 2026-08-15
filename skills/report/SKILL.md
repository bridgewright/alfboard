---
name: report
description: Use this skill after deployment discovery to produce an executive deployment brief and a product input document. It validates the discovery contract, refuses unsupported writing, and keeps customer evidence separate from product recommendations.
---

# Deployment Reporting

The report skill consumes one validated `deployment-discovery.json` and writes two documents:

- `deployment-brief.md`: an executive decision document covering the baseline, bottlenecks, automation priorities, technical prerequisites, indicative economics, and unresolved decisions.
- `product-input.md`: a field-evidence document for the product team covering repeated pain points, needs, affected product surfaces, conditions, edge cases, and open questions. It is not a product requirements document.

## Workflow

1. Use the user-supplied discovery path or `../interview/output/deployment-discovery.json`.
2. If no valid record exists, offer the fictional example in `../../samples/moveon/`; do not draft from missing evidence.
3. Validate the record:

```bash
python3 ../interview/scripts/validate_discovery.py <discovery.json>
```

4. Read `references/deployment-brief-format.md` and `references/costing-assumptions.md`; write the deployment brief.
5. Read `references/product-input-format.md`; write the product input document.
6. Report the evidence source, principal recommendation, strongest field signal, unresolved information, and output paths.

## Guardrails

- Every material statement must trace to a discovery field or be labeled as an assumption.
- Do not evaluate success through automated-resolution rate alone; include repeat contact, response time, staffing, and customer satisfaction where evidence exists.
- Present economics as indicative assumptions, not negotiated pricing or verified savings.
- Describe product considerations and edge cases; do not prescribe an implementation specification on behalf of the product owner.
